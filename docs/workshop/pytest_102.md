# PyTest 102

## Fixtures

### Yield and addfinalizer()

### Built in fixtures

## Conftest

`conftest.py` is automatically discovered and registered by PyTest.

If a fixture appears in many `conftest.py` files then the closes `conftest.py` file to the test is used.

Example is: `02_py_coffee\02_fixtures\test_conftest_2` demonstrating that the closes `conftest.py` fixture value is used. 

## Parametrization

## Customisation by hooks

## Plugins

These are some of the most common plugins.

xdist aside, we can recreate some of the functionality through the use of hooks. The online course 'PyTest Cookbook - Using hooks to create plugins' that you will have a free coupon for will go through this in much more details.

*It is easier than one might think!*

### pytest-csv

We already create our own cutomisable CSV output.

### pytest-html

### pytest-cov

Coverage is an important metric.

### pytest-random

Ideally, all tests are independent of each other and randomising the order should not change the results of the test.

Randomising tests are a good way to test this.

### pytest-xdist

<br>