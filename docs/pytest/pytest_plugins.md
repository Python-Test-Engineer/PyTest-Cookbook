# PyTest_07_PLUGINS

## About

When we create fixtures/hooks in Python, we can enable reuse by putting them in a separate file that is then shared. This is a local plugin ineffect.

If we name the file `conftest.py`, PyTest will automatically digest this file and all files in that same folder will have access to these fixtures/hooks.

Like CSS, we can have many conftest.py files and the child folder `conftest.py` file overrides the parent one.

This file is thus an automatic local plugin.

If we wish to make this distributable then we can create a plugin to upload to PyPi. PyTest_07_PLUGIN has a templated plugin plugin test of the correct form to upload to PyPi.