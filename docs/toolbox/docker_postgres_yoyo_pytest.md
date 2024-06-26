# Docker Postgres Yoyo PyTest

![YoYo](../images/yoyo.png 'YoYo')
## Yoyo

- Repo: https://github.com/Python-Test-Engineer/yt-docker-postgres-yoyo-pytest
- YouTube: due soon...
- YoYo docs: https://ollycope.com/software/yoyo/latest/

Yoyo is a database migration tool like Alembic except it does not use an ORM but SQL.

In the project, yt-docker-postgres-yoyo-pytest, we use Docker and Postgres along with YoYo migrations set up an ecommerce database. We then use PyTest to run structural schema tests.

YoYo acts like Git for our migrations with rollback made possible.

Our DB has PK, FK, Unique and Check constraints and we can access Postgres Schema to run tests on the strucure of the DB:

- Are all the tables there?
- Are all the PKs and FKs there?
- Are all the Unique and Check constraints there?

This is in addition to CRUD testing we may do. This helps ensure that we have not damaged our DB schema during any development.

<br>