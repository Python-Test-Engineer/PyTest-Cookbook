# PyTest 101

## Test discovery

![test-discovery](../images/workshop/test-discvovery.png)
[https://docs.pytest.org/en/stable/explanation/goodpractices.html#conventions-for-python-test-discovery](https://docs.pytest.org/en/stable/explanation/goodpractices.html#conventions-for-python-test-discovery)


## Change location

We can change default in `pytest.ini`:

[https://docs.pytest.org/en/stable/example/pythoncollection.html](https://docs.pytest.org/en/stable/example/pythoncollection.html)

![change test discovery](../images/workshop/change-test-discovery.png)

## Create a test

If we have a function `src\some_function.py` and we want to test it, we can run this function within a test and PyTest will excute it and store results etc:

```
def test_some_function_works.py():
    actual_result = some_function()
    expecterd_result = "expected result values here"
    assert actual_result == expected_result, "(optional) output message if not equal"
```
## Run a test

To run tests we run `python -m pytest`. We can run just `pytest` but running it as a module adds the path to sys.path and can avoid any future issues.

![why python -m](../images/workshop/why-python-m.png)
[https://docs.pytest.org/en/stable/how-to/usage.html#other-ways-of-calling-pytest](https://docs.pytest.org/en/stable/how-to/usage.html#other-ways-of-calling-pytest)

## Selecting tests

### Locations

We can select tests by their location, module, class or function:

![location-selection](../images/workshop/run-by-location.png)
[https://docs.pytest.org/en/stable/how-to/usage.html#specifying-which-tests-to-run](https://docs.pytest.org/en/stable/how-to/usage.html#specifying-which-tests-to-run)

These are called nodes:

`python -m pytest .\tests\00_check_setup\test_01_setup.py`

`python -m pytest .\tests\00_check_setup\test_01_setup.py::test_0001_SET_pass`
### -k

We can select test that are 'like' with the `-k` option:

`python -m pytest -k 0001 ` to select a specific id or

`python -m pytest -k SET` will select all those that contain 'SET' in test name.

We can combine 'not', 'or', 'and':

`python -m pytest -k "not SQL"` will get all tests that contain SET (case insensitive) or SQL. 

This can get tricky for more complex queries and in those case we will use 'markers' particularly as we can create dynamic markers that are based on Python list manipulation. We will se this later.


### Markers

Markers are 'tags' which we can add to tests using `@pytest.mark.tag_name` and we can then select a particular marker using `pytest -m pytest -m tag_name`.

```
@pytest.mark.tag_name
def test_use_marker_tag_name():
    assert True
```

We can assign the name of the marker after @pytest.mark

We do not need to register them with `pytest.ini` provided we do not have `strict` in `addopts`. If we do, we will get an error, if we don't we will get warnings.

In our `pytest.ini` we haf:

```
markers =
    ;add markers of group tests - can use
    ; after colon is optional description
    setup: set up tests
    sanity: sanity tests
    mocks: all mocks
    joke_mocks: mocks for jokes
    add: test add
    inner_marker: an inner marker
    outer_marker: an outer marker
    outer
    inner
    deposit
    withdrawal
    banking
```

In this case above, iff we have 
```
addopts = strict
```
then any markers not registered will cause an error.

If we run `python -m pytest -m sanity` we will get all those that have a marker of `sanity`.

We can also use `not`: `python -m pytest -m "not sanity"`

We can also mark a whole Class and all method tests within will be selected.

[Multiple markers? Seems difficult but later we will see how we can create markers dynamically and thus create one 'super marker'.](https://github.com/pytest-dev/pytest/issues/6142)

[https://docs.pytest.org/en/stable/example/markers.html#working-with-custom-markers](https://docs.pytest.org/en/stable/example/markers.html#working-with-custom-markers)

Multiple markers: https://github.com/pytest-dev/pytest/issues/6142

#### Strict mode

In `pytest.ini` we have `addopts`

#### Dynamic markers

We will not discuss this yet but it is worth mentioning because managing 500+ test markers is best done dynamically...

We can use a hook `pytest_collect_modifyitems()`...

## Output options

[https://docs.pytest.org/en/7.1.x/how-to/output.html](https://docs.pytest.org/en/7.1.x/how-to/output.html)

```
pytest --showlocals     # show local variables in tracebacks
pytest -l               # show local variables (shortcut)
pytest --no-showlocals  # hide local variables (if addopts enables them)

pytest --capture=fd  # default, capture at the file descriptor level
pytest --capture=sys # capture at the sys level
pytest --capture=no  # don't capture
pytest -s            # don't capture (shortcut)
pytest --capture=tee-sys # capture to logs but also output to sys level streams

pytest --tb=auto    # (default) 'long' tracebacks for the first and last
                     # entry, but 'short' style for the other entries
pytest --tb=long    # exhaustive, informative traceback formatting
pytest --tb=short   # shorter traceback format
pytest --tb=line    # only one line per failure
pytest --tb=native  # Python standard library formatting
pytest --tb=no      # no traceback at all
```

### -v, -vv, -vvv

### -s

### -q

### -x

```
pytest -x            # stop after first failure
pytest --maxfail=2    # stop after two failures
```

### -r

[https://docs.pytest.org/en/8.2.x/how-to/output.html#producing-a-detailed-summary-report](https://docs.pytest.org/en/8.2.x/how-to/output.html#producing-a-detailed-summary-report)

```
f - failed

E - error

s - skipped

x - xfailed

X - xpassed

p - passed

P - passed with output

Special characters for (de)selection of groups:

a - all except pP

A - all

N - none, this can be used to display nothing (since fE is the default)
```

### CSV

We can use `pytest-csv` but our custom local plugin `conftest.py` can do this for us.

There is an explainer video for this and we will look at this a bit later.

<br>
