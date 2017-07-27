---
layout: post
title: "Computing Project: Getting Started 2: Electric Boogaloo"
author: Jo Jerrica Decker
categories:
  - The Wayside
  - Final Year Project
  - ShelfLife
---

Upon creation of a Django project, the first order of business was to ensure that the small testing server that ships with the framework, as well as the initial project itself, was in working order before pressing on with anything else. To that end, this was a simple case of moving to the project root and running the following:[[1]]

{% highlight shell %}
python3 manage.py runserver
{% endhighlight %}


This command runs a small webserver for the purposes of development and testing, and as such is not intended for production servers, for which the likes of Apache or Nginx would be better suited.[[1]]


If all had gone well, the output to the command line would look similar to this:[[1]]

[![alt text][great-success]][great-success]


The red warning could be disregarded for the time being, as at this moment, there were no databases to which migrations could be applied.[[1]] Regardless, the server was running and was hopefully accessible at `http://127.0.0.1` on port `8000`. As such, the next step was to open a web browser and enter `http://127.0.0.1:8000/` into the address bar, after which the following page would appear:

[![alt text][definite-success]][definite-success]


Satisfied, the server can then be closed down by returning to the terminal and pressing `Ctrl+C`, and work can commence.


It should be noted that the server can be made to listen on other ports by passing the port to runserver as an additional argument, and similarly, the IP address to which it can listen can also be passed.[[1]]


{% highlight shell %}
python3 manage.py runserver 8080

python3 manage.py runserver 127.0.0.6:8080
{% endhighlight %}


Additionally, the server can listen on all available public IPs by passing `0` (shorthand for the address `0.0.0.0`) in place of a full address:[[1]]


{% highlight shell %}
python3 manage.py runserver 0:8000
{% endhighlight %}


The next step was to create an app. An app is essentially a web application built to serve a specific purpose, said purpose varying depending on one's needs. An app can be anything from a blogging system, to a database management system, to a simple polling application, and the project server to maintain the configurations and apps that comprise a Django-based website as a whole.[[1]]


The intended design of ShelfLife would require the use of many of these apps, each one using its own database. Although maintaining cross-database relationships is impossible in Django, it should be possible to implement necessary workarounds in Python as and when the need arises.


To start things off, the first app - organisations - was created with the following command:[[1]]


{% highlight shell %}
python3 manage.py startapp organisation
{% endhighlight %}


This creates a new folder of the name organisation within the project folder, in its root, and establishes the following basic initial template from which the creation of a new app can be commenced:[[1]]


{% highlight shell %}
organisation/
├── admin.py
├── apps.py
├── __init__.py
├── migrations
│   └── __init__.py
├── models.py
├── tests.py
└── views.py
{% endhighlight %}


Next, per Django's own tutorial, a basic "Hello World" view was created, within the file `views.py`:[[1]]


{% highlight python %}
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the organisation index.")
{% endhighlight %}


That's literally all it takes to create a single basic view to get things started, though a fully fledged view will no doubt become increasingly complex. For the time being though, this was sufficient. The next thing that was required was to map the view to a URL, in order to allow it to be accessed and viewed in a browser. This required the addition of a new file within organisations, called `urls.py`, and the following to be entered into that file:[[1]]


{% highlight python %}
from django.conf.urls import url

from . import views

urlpatterns = [
    url(r'^', views.index, name="index"),
]
{% endhighlight %}


With that done, the existing `urls.py` file within the folder `shelflife` also required an update, to add a reference to the new file:[[1]]


{% highlight python %}
from django.conf.urls import include, url
from django.contrib import admin

urlpatterns = [
    url(r'^organisation/', include('organisation.urls')),
    url(r'^admin/', admin.site.urls),
]
{% endhighlight %}


The reference to the admin app provided by Django had already been automatically generated with the newly-created project, and as such the url and admin imports were already present. To accomodate the organisation app, it became necessary to import an additional method from the `django.conf.urls` module, which was subsequently used to reference the new URL configuration file created within the organisation app.[[1]]


Finally, it was possible to test the new view. The development server was executed again and a browser once again pointed toward `http://127.0.0.1:8000`:[[1]]


[![alt text][hello-world]][hello-world]


With that confirmed, it was time to move on setting up the necessary databases.


## References

1. *Writing your first Django app, part 1* (no date) Available at: https://docs.djangoproject.com/en/1.11/intro/tutorial01/ (Accessed: 14 April 2017).

[1]: https://docs.djangoproject.com/en/1.11/intro/tutorial01/

[great-success]: /assets/images/4e481797-4b3f-4227-b4f5-821de038cd41.png "Great success?"
[definite-success]: /assets/images/0f36a0d1-eaf1-4a57-8790-21e5969b6e80.png "Great success. A little it pushy, though."
[hello-world]: /assets/images/55e345fd-676c-4547-b8be-497cbc09e3d8.png "Hello!"
