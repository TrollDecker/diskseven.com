---
layout: post
title: "Computing Project: Analysis"
author: Jo Jerrica Decker
categories:
  - The Wayside
  - Final Year Project
  - ShelfLife
---

* The system will be created using Python and the Django web framework, due in part to my own familiarity with the Python language and their permissive open-source licenses that would allow the use of the software in both commercial and non-commercial projects without any fees. Django supports PostgreSQL by default, which offers a number of features that would be beneficial to my goals.[1][[2]][[3]][[4]][[5]][[6]][[7]]
* Research of other similar services has included services such as MusicBrainz, which does acheive a lot of similar goals to my own project, though remains strictly focused on music releases. I noted that MetaBrainz collaborates with the Internet Archive to run a separate service, the Cover Art Archive, form which MusicBrainz draws the cover art for each release, if available, and also provides links to services such as ISNI, which provides unique identifiers for personalities who may operate under multiple stage names or share a name with other artists.[[8]][[10]][[11]]
* Additionally, proprietary services such as the Internet Movie Database and a number of comic book databases have been examined, though most appear to lack some of the key requirements I had set for my own project, such as an API or the ability to adequately accomodate certain factors regarding a media release (such as trade paperbacks of comics).[[9]]
* Future research will entail the specifics of each type of media release, to further understand the data I would need to store in the system. This may extend beyond the obvious details such as movies having national age ratings and books having an ISBN number etc.
* I initially considered simply resorting to Azure for deployment, for the sake of ease, though recently I have also discovered Digital Ocean, and may consider deploying there instead, though my final decision will ultimately owe itself to personal experience.

## References

1. Hourieh, A. (2008) *Learning Website Development with Django : A Beginner's Tutorial to Building Web Applications, Quickly and Cleanly with the Django Application Framework.* Birmingham: Packt Publishing.
2. Django Software Foundation (no date) *The web framework for perfectionists with deadlines.* Available at: https://www.djangoproject.com/ (Accessed: 25 February 2017).
3. Python Software Foundation (no date) *Welcome to Python.org.* Available at: https://www.python.org/ (Accessed: 25 February 2017).
4. The PostgreSQL Global Development Group (no date) *PostgreSQL: The world's most advanced open source database* Available at: https://www.postgresql.org/ (Accessed: 25 February 2017).
5. The Open Source Initiative (no date) *The PostgreSQL Licence (PostgreSQL)* Available at: https://opensource.org/licenses/postgresql (Accessed: 25 February 2017).
6. The Open Source Initiative (no date) *Python License (Python-2.0)* Available at: https://opensource.org/licenses/Python-2.0 (Accessed: 25 February 2017).
7. The Open Source Initiative (no date) *The 3-Clause BSD License* Available at: https://opensource.org/licenses/BSD-3-Clause (Accessed: 25 February 2017).
8. MetaBrainz Foundation (no date) *MusicBrainz - The Open Music Encyclopedia* Available at: https://musicbrainz.org (Accessed: 25 February 2017).
9. MetaBrainz Foundation, Internet Archive (no date) *Cover Art Archive* Available at: coverartarchive.org (Accessed: 25 February 2017).
10. IMDb.com, Inc. (no date) *IDMb - Movies, TV and Celebrities - IMDb* Available at: www.imdb.org (Accessed: 25 February 2017).
11. ISNI International Agency (no date) *ISNI* Available at: www.isni.org (Accessed: 25 February 2017).

[2]: https://www.djangoproject.com/
[3]: https://www.python.org/
[4]: https://www.postgresql.org/
[5]: https://opensource.org/licenses/postgresql
[6]: https://opensource.org/licenses/Python-2.0
[7]: https://opensource.org/licenses/BSD-3-Clause
[8]: https://musicbrainz.org
[9]: coverartarchive.org
[10]: www.imdb.org
[11]: www.isni.org
