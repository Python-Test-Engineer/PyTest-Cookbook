# Docker

## My Docker-Postgres setup
- My Docker-Postgres-PgAdmin-Adminer set up: [Docker-Postgres-PgAdmin-Adminer](https://pytest-cookbook.com/toolbox/docker_postgres_setup/)

## Using YoYo migrations

Using our Docker Postges set up with YoYo for database migrations and versioning [YoYo](https://ollycope.com/software/yoyo/latest/).

## Docker-PyTest plugin

Located in `tests/_isolated_suites/docker-pytest-poetry-fixtup-RUN_ISOL`

This is based on the following article: 

- https://dev.to/farcellier/test-beyond-your-code-with-docker-pytest-3b7g


I have included it here for reference. It won't work with PyTest-Full-Stack and needs to be in its own separate suite.

Open tests/_isolated_suites/docker-pytest-poetry-fixtup-RUN_ISOL in own IDE

- `python -m venv venv`
- `.\venv\Scripts\activate` or Mac equivalent
- `pip install -r requirements.txt`

- ensure you remove REACTIVATE_ from front of test_postgressql_database.py so PyTest can discover this test. It was made invisible in this way so it did not collide and fail running of PFS default set up.
- `python -m pytest .\tests\test_postgressql_database.py -vs`

*Make sure docker is running!*

There is a YT video of this: [pytest-docker](https://youtu.be/m80NeP_Jtp4)

