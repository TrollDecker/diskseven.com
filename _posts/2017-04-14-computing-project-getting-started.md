---
layout: post
title: "Computing Project: Getting Started"
author: Jo Jerrica Decker
categories:
  - The Wayside
  - Final Year Project
  - ShelfLife
---

Initial prerequisites for developing ShelfLife:


* Python 3, required for Django as the framework no longer supports Python 2. Installation depends on the OS, but most Ubuntu/Debian-based Linux distributions can install it via apt using the following command, should it be absent from one's system:

{% highlight shell %}
sudo apt-get install python3
{% endhighlight %}

* In addition, while most package managers provide many of the libraries available for Python in both its versions, it is usually recommended to use the pip package installer to install these instead, as a distribution's package manager can often be several versions behind. As Python is available in two separate and somewhat different versions, separate versions of pip exist for those versions. For the purposes of this project, pip3 will be used. If this is absent from one's system, it can be installed via a package manager or invoking cURL (example for Python 2):[[3]]

{% highlight shell %}
curl https://bootstrap.pypa.io/get-pip.py | python
{% endhighlight %}

* Django: The framework of choice for this project. This will be installed using pip in order to ensure the latest version has been installed.[[4]] At the time of install, the Python 3 version of pip is installed on Debian-based distros as pip3, possibly to avoid conflicts with Python 2.

{% highlight shell %}
sudo pip3 install django
{% endhighlight %}

* PostgreSQL. The database of choice for this project. This can be installed via the package manager, though binaries and source are also available from the project's website.[[5]]

{% highlight shell %}
sudo apt-get install postgresql-9.4
{% endhighlight %}

Note that the installation process may create a system user called "postgres", which acts as a superuser for accessing and modifying databases on the installed system.[[6]]


Once those were installed, a new Django project can be created by navigating to the folder the folder that will host the project files for the time being using cd. Once there, a new project folder can be created with the following command[[1]]:

{% highlight shell %}
django-admin startproject <site-name>
{% endhighlight %}

Where `<site-name>` will be the name of the project, in the case of this particular project, "shelflife". The immediate result of this command will be the creation of the following folder structure[[1]][[2]]:

{% highlight shell %}
shelflife/
├── manage.py
└── shelflife
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
{% endhighlight %}

As an alternative, a full stop can be appended to the command, and instead of creating a new root folder for the project, the current folder will be used as the project root.[[2]] Note that the root folder can take any name, and thus be rename to just about anything desired, without any detriment to the operation of the project.[[1]]


## REFERENCES

1. *Writing your first Django app, part 1* (no date) Available at: https://docs.djangoproject.com/en/1.11/intro/tutorial01/ (Accessed: 14 April 2017).
2. *Your first Django Project!* (no date) Available at: https://tutorial.djangogirls.org/en/django_start_project/index.html (Accessed: 14 April 2017).
3. 'Pip (package manager)' (2017) *Wikipedia.* Available at: https://en.wikipedia.org/wiki/Pip_(package_manager) (Accessed: 14 April 2017).
4. *How to install Django* (no date) Available at: https://docs.djangoproject.com/en/1.11/topics/install/ (Accessed: 14 April 2017).
5. *PostgreSQL: Linux downloads (Ubuntu)* (no date) Available at: https://www.postgresql.org/download/linux/ubuntu/ (Accessed: 14 April 2017).
6. *PostgreSQL: Documentation: 9.6: Creating a Database* (no date) Available at: https://www.postgresql.org/docs/9.6/static/tutorial-createdb.html (Accessed: 14 April 2017).

[1]: https://docs.djangoproject.com/en/1.11/intro/tutorial01/
[2]: https://tutorial.djangogirls.org/en/django_start_project/index.html
[3]: https://en.wikipedia.org/wiki/Pip_(package_manager)
[4]: https://docs.djangoproject.com/en/1.11/topics/install/
[5]: https://www.postgresql.org/download/linux/ubuntu/
[6]: https://www.postgresql.org/docs/9.6/static/tutorial-createdb.html
