# PyTest Hooks

## Hooks

PyTest has many hooks that we can tap into such as 'seesion_start'. 'make_report'

We can use conftest.py as a central location to add our own implementations when these hools run/

## PyTest_08_HOOKS

## Install 

- move to `PyTest_08_HOOKS` 
- create virtual environment as you wish
- run `pip install requirement.txt`

## Run Tests

- run `python -m pytest -vs`
- you will se output of accessible variables in PyBoxen, (a console formatter based on Rich).
- Test restults are exported toa CSV in the `pytest_runtest_makereport` hook.


## TODO

