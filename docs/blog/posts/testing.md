---
date: 2024-02-03
---
# FOSDEM'24

## Location

[https://github.com/Python-Test-Engineer/PYTHON-TEST-FRAMEWORK](https://github.com/Python-Test-Engineer/PYTHON-TEST-FRAMEWORK)

## Purpose

DB integrity

Test existence and integrity of tables, foreign keys, constraints etc.

## Uses

- SQL Model
- SQLModel's `inspect` feature.

## Information

SQLModel is a library for interacting with SQL databases from Python code, with Python objects. It is designed to be intuitive, easy to use, highly compatible, and robust.

SQLModel is based on Python type annotations, and powered by Pydantic and SQLAlchemy. https://sqlmodel.tiangolo.com/

We can get metadata on tables/views to check:

- Check tables and views exist.
- Check foreign keys, defaults, unique constraints, nullability and more.
- And more...

We will work with an SQLite example but the SQLModel engine feature enables the same code to be used on a variety of databases.

## YouTube

[https://youtu.be/vcRB_pg__AQ](https://youtu.be/vcRB_pg__AQ)