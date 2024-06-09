# PyTest and Docker

## Demo One

PyTest-Full-Stack has an example using `pytest-docker`.

*Ensure docker desktop or equivalent is running!* 😬 

Located in tests/docker. My usual folder naming of 70_docker is unacceptable so I just use docker.

There is a YT video of this: [pytest-docker](https://youtu.be/43YKqEg49HI)

## Demo Two

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


## Other plugins

There are a number of docker plugins for pytest:

- `pytest-docker-compose`
- `pytest-docker-tools`
- `docker-python-unittest-pytest` is a more DIY setup.

## Docker-Postgres-PGAdmin-Adminer - to go

I have a [YT video](https://www.youtube.com/watch?v=mipRKPHwlBk )and [repo](https://github.com/Python-Test-Engineer/yt-docker-postgres-pgadmin-adminier-python-sql) that I have tested many times myself. It also uses my custom Postgres image which has PGVector extension added, (Vector DB uses).   

<br>


