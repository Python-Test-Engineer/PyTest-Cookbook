# PyTest and Docker

## Demo One

PyTest-Full-Stack has an example using `pytest-docker`.

*Ensure docker desktop or equivalent is running!* 😬 

Located in tests/docker. My usual folder naming of 70_docker is unacceptable so I just use docker.

## Demo Two

Located in `tests/docker-pytest-poetry-fixtup-RUN_ISOL`

This is based on the following article: 

 - https://dev.to/farcellier/test-beyond-your-code-with-docker-pytest-3b7g

Copy and run from outside PyTest-Full-Stack.

I have included it here for reference. It won't work with PyTest-Full-Stack and needs to be in its own separate suite.

- `python -m venv venv`
- `.\venv\Scripts\activate` or Mac equivalent
- `pip install -r requirements.txt`
- `python -m pytest .\tests\test_postgressql_database.py -vs`

*Make sure docker is running!*

## Other plugins

There are a number of docker plugins for pytest:

- `pytest-docker-compose`
- `pytest-docker-tools`
- `docker-python-unittest-pytest` is a more DIY setup.
