# PyTest Extended

## About PyTest Extended

PyTest Extended is a set of separate and self contained test suites focussing on a more advanced aspect of PyTest.

- DB Testing focusses on testing SQL Schemas for integrity of foreign keys, constraints etc. This ensures that code development does not break the underlying data model.
- Hooks looks at a number of PyTest hooks to be able to order tests for example, create a CSV-Lite report, use dynamically generated parametrized data sets and so on.
- Plugins looks at how we can create our own distributable plugins as well as how to test with PyTester.
- CLI Apps is an demo of testing a CLI app with PyTest.
- CI Integration and Tox are examples of testing our apps on a variety of Python Versions and with GitHub Actions how to test multiple Python Versions across a number of OS.
