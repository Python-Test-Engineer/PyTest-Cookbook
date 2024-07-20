# Docker Postgress PgAdmin Adminer

It has both PgAdmin and Adminer as Postgress clients.

There are range of SQL Crud files included so that you have Python-Docker-Postgres working.

I had some issues with this type of set up but came up with my own docker-compose file.

[YouTube Video](https://www.youtube.com/watch?v=mipRKPHwlBk&list=PLsszRSbzjyvmgwrK911sdv03peQlGirym)

The repo is here: [GitHub](https://github.com/Python-Test-Engineer/yt-docker-postgres-pgadmin-adminer-python-sql)

There are a number of ways to set up a volume - named or bind mount.

The latter use a folder within your project, whereas a named volume is managed by Docker and persists after the container is stopped.

The repo has docker-compose.yaml files for both types.

Bind mount volume:

```
volumes:
   - ./db-data/:/var/lib/postgresql/data/
```
Named volume:
```
volumes:
   - data:/var/lib/postgresql/data/
```

Additonally, this video looks at setting up scripts automatically:
[https://www.youtube.com/watch?v=EtWTa27G4wE](https://www.youtube.com/watch?v=EtWTa27G4wE).

<br>