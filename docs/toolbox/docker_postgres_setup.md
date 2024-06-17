# Docker Postgress PgAdmin Adminer

This uses my Postgres image that has the VectorDB extension installed, (for semantic search).

It has both PgAdmin and Adminer as Postgress clients.

There are range of SQL Crud files included so that you have Python-Docker-Postgres working.

I had some issues with this type of set up but came up with my own docker-compose file.

[YouTube Video](https://www.youtube.com/watch?v=mipRKPHwlBk&list=PLsszRSbzjyvmgwrK911sdv03peQlGirym)

The repo is here: [GitHub](https://github.com/Python-Test-Engineer/yt-docker-postgres-pgadmin-adminier-python-sql)

There are a number of ways to set up a volume.

For me, the following saved the Postgres data:

```
volumes:
   - ./db-data/:/var/lib/postgresql/data/
```

and it uses the default storage location for data in Postgres.

Using the named volume approach gave me a few issues.

<br>