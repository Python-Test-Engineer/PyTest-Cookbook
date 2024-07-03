# Advanced Docker 

This is a selection of less shown aspects of Docker, not necessarily advanced Docker but more uncommon.

Under construction 🏗️

## 'version' deprecated

A `docker-compose.yaml` file no longer needs the `VERSION` at top.

One can also use a different named file with the `-f` flag: `docker compose -f another_file.yaml up` and we can avoid the use of `docker-compose` in favor of `docker compose`.


## Depends On

[https://www.warp.dev/terminus/docker-compose-depends-on](https://www.warp.dev/terminus/docker-compose-depends-on)

Whilst `depends on` defines a dependency, to check that the service is running we can use:

```
services:
  api:
    build: .
    depends_on:
      database:
        condition: service_started
  database:
    image: postgres

```

```
services:
  api:
    build: .
    depends_on:
      database:
        condition: service_healthy
  database:
    image: postgres
    healthcheck:
      test: ["CMD-SHELL", "pg_isready"]
```
```
services:
  api:
    build: .
    depends_on:
      database:
        condition: service_healthy
      migration:
        condition: service_completed_successfully
  database:
    image: postgres
    healthcheck:
      test: ["CMD-SHELL", "pg_isready"]
```

## Develop and watch

There is an alternative way for reloading without rebuilding that does not need bind mounts:

![Compose Develop](../images/docker/compose-watch-dockercon2023.png  'develop')

[DockerCon2023 Video on Compose Develop](https://www.youtube.com/watch?v=u1q8AyNMxd4)


Docs: [https://docs.docker.com/compose/file-watch/](https://docs.docker.com/compose/file-watch/)



```
services:
  web:
    build: .
    command: npm start
    develop:
      watch:
        - action: sync
          path: ./web
          target: /src/web
          ignore:
            - node_modules/
        - action: rebuild
          path: package.json
```

We can set either `rebuild` if the image needs rebuilding when we change requirements.txt for example and we can use `sync` when our code changes.

`sync+restart` is ideal when config file changes, and you don't need to rebuild the image but just restart the main process of the service containers. It will work well when you update a database configuration or your nginx.conf file for example

## Labels

Labels are useful to add metadata:

```
FROM ubuntu:latest
LABEL "website.name"="example.com"
LABEL maintainer="me"
LABEL website="geeksforgeeks"
LABEL desc="This is docker tutorial"
```

## Overide, include and merge

Files can be overriden, merge or have include files.

[https://docs.docker.com/compose/multiple-compose-files/extends/#extending-services-from-another-file](https://docs.docker.com/compose/multiple-compose-files/extends/#extending-services-from-another-file)]

For example:

`docker compose -f compose.yml -f compose.admin.yml run backup_db`
The compose.yml file might specify a webapp service.

```
webapp:
  image: examples/web
  ports:
    - "8000:8000"
  volumes:
    - "/data"
  environment:
    - DEBUG=1
```
The compose.admin.yml may also specify this same service:

```
webapp:
  ports:
    - "9000:8000"
  environment:
    - ANOTHER_VARIABLE=value
```
Any matching fields override the previous file. New values, add to the webapp service configuration:

```
webapp:
  image: examples/web
  ports:
    - "9000:8000"
  volumes:
    - "/data"
  environment:
    - DEBUG=1
    - ANOTHER_VARIABLE=value
```
## Multi stage builds

Many times, one part of the build creates artificacts that are used in the main image.

By using multi stage builds, the artifiact and not the images needed to create them are used in the main image build.

For example, we might build an artifact in Cpython to use in our image build. We don't want the Cpython compiler image included in the final image, just the code.

[https://medium.com/@ketangangal98/docker-201-multi-stage-builds-for-production-59b1ea98924a](https://medium.com/@ketangangal98/docker-201-multi-stage-builds-for-production-59b1ea98924a)

## Securing secrets

The video below is a very good explainer of how 'secrets' can be exposed and how to prevent this.

[YouTube](https://www.youtube.com/watch?v=aK6sJDOn2Hc)