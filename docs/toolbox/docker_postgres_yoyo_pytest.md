# Docker Postgres Yoyo PyTest

![YoYo](../images/yoyo.png 'YoYo')

## Yoyo

- Repo: https://github.com/Python-Test-Engineer/yt-docker-postgres-yoyo-pytest
- YouTube: due soon...
- YoYo docs: https://ollycope.com/software/yoyo/latest/

Yoyo is a database migration tool like Alembic, except it does not use an ORM but SQL.

In thisproject, yt-docker-postgres-yoyo-pytest, we use Docker and Postgres along with YoYo migrations to set up an ecommerce database. 

Using various SQL scripts, we can get a list of all constraints - PK, FK, Defaults, Unique and Check - which can then be used to carry out structural testing to ensure that database intgerity is preserved during development.

YoYo acts like Git for our migrations with rollback made possible.

`yoyo new -m "add foreign keys"` creates a file in the `migrations` folder that has 'steps' of SQL and their rollback. The file has a name of `datestamp-random_chars-message_used.py`.

![MIGRATIONS](../images/yoyo-migrations-folder.png  "Migrations")


![STEPS](../images/yoyo-steps.png  "steps")

*There can be many steps in a file.*

The `sql_schema folder` contains scripts to query the schema tables for all constraints.

The `steps` folder has just the steps for reuse and archice.

The `sql_postgres` folder has a number of python CRUD files that connect to the docker-postgres instance to act as a set up check and utilities.

`yoyo.ini` is a configurtion file that has minimal required settings for source of yoyo migration files, (migrations usually), and the DB connection URL:

```
sources = %(here)s/migrations
; both host.docker.internal and localhost work
database = postgresql://postgres:postgres@host.docker.internal/postgres?port=5432
```

In the video, you will see examples of building up a number of migration files and alos how to rollback one, many or all migrations.

Our DB has PK, FK, Unique and Check constraints and we can access Postgres Schema to run tests on the strucure of the DB:

- Are all the tables there?
- Are all the PKs and FKs there?
- Are all the Unique and Check constraints there?

This is in addition to CRUD testing we may do. This helps ensure that we have not damaged our DB schema during any development.

The project also includes a folder of sql_postgress python modules to perfome CRUD etc.

It uses the standard [docker-postgres-pgadmin-adminer-python-sql](https://github.com/Python-Test-Engineer/yt-docker-postgres-pgadmin-adminier-python-sql) project to set up Docker Postgres.

<br>