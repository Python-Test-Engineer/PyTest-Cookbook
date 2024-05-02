# PyTest

## If we didn't have PyTest,  what might we do?

If we had to test a set of functions without PyTest, we might do the following:

- Write code in a test function.
- Have a naming convention to detect testing functions.
- Execute the test functions and store the assert value.
- Add in some useful helpers to create a report, to add makers so that we can run tests selectively.
- etc

PyTest does this and far more for us. It uses [Pluggy](https://github.com/pytest-dev/pluggy){target="_blank"}, to provide a plugin based architecture so that we can use a variety of plugins.

[pytest-dev](https://github.com/pytest-dev){target="_blank"} hosts a variety of plugins. 

PyTest docs has a list of over 1000 plugins -  [PyTest Plugins](https://docs.pytest.org/en/7.1.x/reference/plugin_list.html){target="_blank"}.

## PyTest incremental test suites

There are four test suites that build on each other:

- PyTest_00_MINIMAL is a bare bone wiring of a src folder and tests with custom logging set up in pytest.ini
- PyTest_01_MAIN is a comprehensive test suite with numerous template tests for most of the features of PyTest along with templates for mocking and patching. An async set of tests are also included. Combined with references to YT videos, and some utilities, this is a fundamental test suite.
- PyTest_02_API_PLAYWRIGHT uses Playwright to carry out API tests as well as e23 or end user automated tests.
- PyTest_03_BDD has an implementation of the `pytest-bdd` plugin for Behaviour Driven Testing/Development.

## Stand alone test suites

The remaining test suites are all stand alone and do not contain any of the first four test suites.

Test files can be ported to any of the test suites.

## Suggested use

Start with PyTest_01_MAIN and once set up run `python -m pytest -vs` to see over a 100 tests run with `pytest-sugar` formatted output.

The `02_py_coffee` folder in tests as well as `03_indian_pythonista` are two very good tutorials with accompanying YT videos.