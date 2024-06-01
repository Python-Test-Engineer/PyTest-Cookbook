# PyTest Full Stack - continually developing...

## Configurable, templated

A configurable, templated full stack Python PyTest Framework

If we had to test a set of functions without PyTest, we might do the following:

- Write code in a test function.
- Have a naming convention to detect testing functions.
- Execute the test functions and store the assert value.
- Add in some useful helpers to create a report, to add makers so that we can run tests selectively.
- etc

PyTest does this and far more for us. It uses [Pluggy](https://github.com/pytest-dev/pluggy){target="_blank"}, to provide a plugin based architecture so that we can use a variety of plugins.

[pytest-dev](https://github.com/pytest-dev){target="_blank"} hosts a variety of plugins. 

PyTest docs has a list of over 1000 plugins -  [PyTest Plugins](https://docs.pytest.org/en/7.1.x/reference/plugin_list.html){target="_blank"}.

## Full Stack

This framework has tests covering:

- SQL Schemas for foreign keys, number of tables, check constraints etc...
- Unit tests
- Mocks, patches and monkey patches
- Behavior Driven Testing templates
- API testing
- End to End testing with Playwright

## YouTube videos

Videos are available at: [YouTube]([PyTest Full Stack](https://github.com/Python-Test-Engineer/PYTHON-TEST-FRAMEWORK))

## Repo

The repo is available at: [PyTest Full Stack](https://github.com/Python-Test-Engineer/PYTHON-TEST-FRAMEWORK)

## Suggested use

Start with PyTest_01_MAIN and once set up run `python -m pytest -vs` to see over a 100 tests run with `pytest-sugar` formatted output.

The `02_py_coffee` folder in tests as well as `03_indian_pythonista` are two very good tutorials with accompanying YT videos.