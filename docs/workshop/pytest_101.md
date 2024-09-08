# PyTest 101

## Create a test

## Run a test

## Selecting tests

### Locations

### -k

### Markers

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
