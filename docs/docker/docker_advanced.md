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

[https://docs.docker.com/compose/file-watch/](https://docs.docker.com/compose/file-watch/)

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

### Overide and merge

### Multi stage builds

### Securing secrets