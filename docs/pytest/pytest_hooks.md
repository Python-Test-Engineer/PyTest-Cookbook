# PyTest_08_HOOKS

This is an isolated test suite to demonstrate variables etc accessible during a PyTest run.

## Hooks

PyTest has many hooks that we can tap into such as 'seesion_start'. 'make_report'

We can use conftest.py as a central location to add our own implementations when these hooks run.

In the conftest.py, we add hooks for:

- pytest_configure
- pytest_sessionstart
- pytest_sessionfinish
- pytest_collection_modifyitems - this gathers tests it will do and can display without running tests. One can sort by property as well as add markers dynamically
- pytest_runtest_makereport - we get test results and export to CSV.

There are many more. A useful article on hooks: https://paragkamble.medium.com/understanding-hooks-in-pytest-892e91edbdb7


## Install 

- move to `PyTest_08_HOOKS` 
- create virtual environment as you wish
- run `pip install requirements.txt`

## Run Tests

- run `python -m pytest -vs`.
- you will se output of accessible variables in PyBoxen, (a console formatter based on Rich).
- some more verbose information has been commented out.
- Test results are exported to ab output file report_NNNN.tyt in the `pytest_runtest_makereport` hook. It is `|` pipe delimited. One can read and extract relevant infomation of test that will be run.

## TODO:

 Important ones are pytest_collection_modifyitems to reorder tests if needed or add markers and pytest_runtest_makereport which can create our own custom output file


