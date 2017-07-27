---
layout: post
title: "Computing Project: Database Design"
author: Jo Jerrica Decker
categories:
  - The Wayside
  - Final Year Project
  - ShelfLife
---

[![alt text][db-design]][db-design]

* **User**: Stores user-specific data such as their personal information and their shelves.
  * **ReleaseShelf** stores many-to-many links between releases and users' shelves (a shelf can hold many releases and a release can be held by many shelves).
* **Edit**: Maintains details of edits made on records, and the votes for and against each one.
  * **Edit** (the eponymous table) maintains a one-to-many relationship with the Release table: a release can be edited many times, but an edit can only affect one release at a time.
  * **Vote** maintains one-to-many relationships with Edit (an edit can be voted upon many times, but a vote only applies on one edit), as well as User (a user can cast many votes, but a vote can only be attributed to one user.
* **Series**: Holds data on a series, the individual volumes within that series, and the type-agnostic data for a release. Includes a NestedRelease table for releases bundled within releases (for example, box sets).
  * In addition to the aforementioned relationships, **Release** is also linked by many-to-many relationships and one-to-many relationships between their more type-specific systems.
  * **ReleaseCover** stores many-to-many links between covers and releases, as it's entirely possible for a single media release to possess alternative covers. An example of this is comics, in which a single issue can release with several available variant covers.
* **Book**: Contains data on books released in a series. This data would not only include paperback and hardback formats, but also magazine formats, allowing the incorporation of comics without the need for a separate database and repeated data for collected editions.
  * The **ReleaseExtra** table maintains an addition foreign-key relationship to a currency table to accommodate the RRPs usually listed on books.
* **Movie**: This table is a bit of a misnomer in one sense, as it would not only include the usual feature-length releases that many associate with the term, but also any kind of motion picture, be it a TV show, short film, documentary, or - of course - feature-length releases, among other possible forms.
  * **FeatureComponent** maintains two additional one-to-many relationships to the Definition and Aspect Ratio tables, allowing such video data to be included in this system's records.
* **Music**: Holds information on music releases that include albums and singles, as well as EPs.
* **Game**: Contains information on videogame releases.
* **Organisation**: Contains information on the organisations involved in the production of a media release.
* **Person**: Holds information in the individual people involved, whether they are real persons directly involved in a release's creation or fictitious characters depicted by that media.
* **Format**: Stores formatting data about a release.
* **International**: Maintains data relevant to a release's national origin and point of sale.
* **Cover**: Maintains data regarding the covers of each release.

[db-design]: /assets/images/ae24fecc-cfdc-4469-b615-5bf194ca064c.png "Database design"
