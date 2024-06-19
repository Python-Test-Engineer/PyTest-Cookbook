# Docker

## My Docker-Postgres setup
- My Docker-Postgres-PgAdmin-Adminer set up: [Docker-Postgres-PgAdmin-Adminer](https://pytest-cookbook.com/toolbox/docker_postgres_setup/)

## Using YoYo migrations

Using our Docker Postges set up with YoYo for database migrations and versioning [YoYo](https://ollycope.com/software/yoyo/latest/).

## Docker-PyTest plugin

This is based on the following article: 

- article: [test-beyond-your-code-with-docker-pytest](https://dev.to/farcellier/test-beyond-your-code-with-docker-pytest-3b7g)
- repo: [repo](https://github.com/Python-Test-Engineer/yt-docker-pytest-poetry-fixtup)
- video: [pytest-docker](https://youtu.be/m80NeP_Jtp4)

Setup:

- `python -m venv venv`
- `.\venv\Scripts\activate` or Mac equivalent
- `pip install -r requirements.txt`
- `python -m pytest -vs`

*Make sure docker is running!*

<br>