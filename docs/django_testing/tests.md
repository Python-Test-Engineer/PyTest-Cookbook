# Tests

These are located within each app under the tests folder. The standard `test.py` is best deleted otherwise the test runner can get confused and tests won't run.

Running `python manage.py test` will run all the tests. `python -m pytest` will also run these tests plus any other tests in root tests folder. For clarification, I have called this folder `pytest-tests`. PyTest searches the whole project for test files.

