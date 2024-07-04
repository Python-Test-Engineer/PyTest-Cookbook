# Docker To Go

I have a range of Docker multi-container apps and the repo is [here](https://github.com/Python-Test-Engineer/yt-docker-to-go).

The following have been added and tested as of 28JUN2024

## Django Sqlite/Postgres

This uses the PythonCRUD-Postgres-PgAdmin-Adminer in the Docker To Go [repo](https://github.com/Python-Test-Engineer/yt-docker-to-go) to set up a Postgres container.

There are a number of settings.py files:
- `settings.py` with default SQLite
- `settings_sqlite.py` with default SQLite
- `settings_postgres.py`with Posgres connection

They can be merged into one with SQLite or Postgres commented out or copy appropriate settings file to `settings.py`.

## FastAPI with reload

FastAPI with hot reload on code change [YouTube](https://www.youtube.com/watch?v=ubHmmKnAoQg)

## PythonCRUD-Postgres-PgAdmin-Adminer 

This has the PythonCRUD-Postgres-PgAdmin-Adminer set up [YouTube](https://www.youtube.com/watch?v=gldHOc65buI).

## Flask-Redis

Details to follow...

## Nginx-Flask-MySQL

Details to follow...