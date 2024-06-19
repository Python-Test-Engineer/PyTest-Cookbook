# Pydantic Utilities

I have a number of utilities based on Pydantic that can be of use.

The idea I am working on is using generators with Pydantic to provide test data to use in the `pytest_generate_tests` hook so that we can decouple large and dynamic test data from PyTest and use Python to load in data dynamically and configured from some sort of config file.

These will be added to the toolbox in due course...