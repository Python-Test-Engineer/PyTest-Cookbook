# Database structural testing

Testing the structural integrity of a database. using SQLModels's `inspect` feature.

SQLModel is a library for interacting with SQL databases from Python code, with Python objects. It is designed to be intuitive, easy to use, highly compatible, and robust.

SQLModel is based on Python type annotations, and powered by Pydantic and SQLAlchemy. https://sqlmodel.tiangolo.com/

We can get metadata on tables/views to check:

- Check tables and views exist.
- Check foreign keys, defaults, unique constraints, nullability and more.
- And more...

We will work with an SQLite example but the SQLModel engine feature enables the same code to be used on a variety of databases.

TODO

Copy model tests from Very FastAPI