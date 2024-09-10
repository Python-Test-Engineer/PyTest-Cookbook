# PyTest 102

## Fixtures

### Definition

[https://docs.pytest.org/en/stable/explanation/fixtures.html](https://docs.pytest.org/en/stable/explanation/fixtures.html)

Fixtures are requested by test functions or other fixtures by declaring them as argument names.

They are an example of dependency injection and replace the setup/teardown features of Unit Test.

Fixtures can thus use other fixtures.

### Implementation

`tests\02_py_coffee\02_fixtures\00_basic_fixtures\test_fiztures_0.py` is an example:

```

@pytest.fixture
def initial_value():
    return 5

def square(num: int) -> int:
    return num * num

# We pass in the fixture - dependency injection
def test_0240_FXT_square(initial_value: int) -> None:
    result = square(initial_value)
    assert result == initial_value**2
```



### Yield and addfinalizer()

```
@pytest.fixture()
def my_object_fixture():
    print("1. fixture code.")
    yield MyObjectThatRequiresCleanUp()
    print("4. fixture code after yield.")
```

### Built in fixtures

There are many built in fixtures provided by PyTest but I only use a few of them:

[https://docs.pytest.org/en/stable/reference/fixtures.html#built-in-fixtures](https://docs.pytest.org/en/stable/reference/fixtures.html#built-in-fixtures)
![built in fixtures](../images/workshop/built-in-fixtures.png)
![built in fixtures](../images/workshop/built-in-fixtures-2.png)

Fixture availability is determined from the perspective of the test. A fixture is only available for tests to request if they are in the scope that fixture is defined in. If a fixture is defined inside a class, it can only be requested by tests inside that class. But if a fixture is defined inside the global scope of the module, then every test in that module, even if it’s defined inside a class, can request it.

## Conftest

`conftest.py` is automatically discovered and registered by PyTest.

If a fixture appears in many `conftest.py` files then the closes `conftest.py` file to the test is used.

Example is: `02_py_coffee\02_fixtures\test_conftest_2` demonstrating that the closest `conftest.py` fixture value is used. 

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