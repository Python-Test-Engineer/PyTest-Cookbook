# PyTest Hooks

## Hooks

PyTest has many hooks that we can tap into such as 'seesion_start'. 'make_report'

We can use conftest.py as a central location to add our own implementations when these hooks run.

- pytest_sessionstart
- pytest_sessionstart
- pytest_collection_modifyitems - this gathers tests it will do and can display without running tests.
- pytest_sessionfinish
- pytest_runtest_makereport - we get test results and export to CSV.

There are many more. A useful article on hooks: https://paragkamble.medium.com/understanding-hooks-in-pytest-892e91edbdb7

## PyTest_08_HOOKS

This is an isolated test suite to demonstrate variables etc accessible during a PyTest run.

## Install 

- move to `PyTest_08_HOOKS` 
- create virtual environment as you wish
- run `pip install requirement.txt`

## Run Tests

- run `python -m pytest -vs`
- you will se output of accessible variables in PyBoxen, (a console formatter based on Rich).
- Test restults are exported toa CSV in the `pytest_runtest_makereport` hook.


## TODO

