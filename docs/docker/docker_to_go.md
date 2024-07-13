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

FastAPI with hot reload on code change [YouTube](https://www.youtube.com/watch?v=ubHmmKnAoQg).

## FastAPI Multi-Stage build

We can use FROM many times with the last FROM being the final image.

To do this we need to use the multi-stage implementation as defined in the docs: [https://docs.docker.com/build/building/multi-stage/](https://docs.docker.com/build/building/multi-stage/).

In this example we use the DockerfileMultiStage file as the Docerfile and carry out the build in the same way. We create an artifact of `test.txt` with the current date and time and copy this into the final image. 

The use case for this is to create cython files for time-consuming modules. We want the binaries but not all the cpython files necessary to build the final binary. 

Using multi-stage builds, we can Dockerise the artifact and copy this into the final image, reducing the final size of the image and the time needed to rebuild it when the binary build does not change but the final image does, e.g. when we change our code and we have reload enabled.

[YouTube Video](https://www.youtube.com/watch?v=r1TE2hkqxCI&list=PLsszRSbzjyvklQ2LAjNEURKYAYglUgHsB&index=2)

## PythonCRUD-Postgres-PgAdmin-Adminer 

This has the PythonCRUD-Postgres-PgAdmin-Adminer set up [YouTube](https://www.youtube.com/watch?v=gldHOc65buI).

## Flask-Redis

Details to follow...

## Nginx-Flask-MySQL

Details to follow...

<br>