# PyTest

## If we din't have PyTest,  what might we do?

If we had to test a set of functions without PyTest, we might do the following:

- Write code in a test function.
- Have a naming convention to detect testing functions.
- Execute the test functions and store the assert value.
- Add in some useful helpers to create a report, to add makers so that we can run tests selectively.
- etc

PyTest does this and far more for us. It uses [Pluggy](https://github.com/pytest-dev/pluggy){target="_blank"}, to provide a plugin based architecture so that we can use a variety of plugins.

[pytest-dev](https://github.com/pytest-dev){target="_blank"} hosts a vareity of plugins. 

PyTest docs has a list of over 1000 plugins -  [PyTest Plugins](https://docs.pytest.org/en/7.1.x/reference/plugin_list.html){target="_blank"}.
