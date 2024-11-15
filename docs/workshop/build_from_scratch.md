# Build from scratch

We have already seen the BASIC demo and the minimum we need to use pytest is a `tests`folder with test files `test_*.py` and pytest installed. This will enable us to do `python -m pytest` to run tests.

To build the PFS framework we can add the following:

## src

Folder for one's source code - optional but recommended location by Python.

We will assume we have our `src` folder.

We can create a virtual environment with `python -m venv venv` followed by activation:

- `.\venv\scripts\activate` for Windows
- `source venv/bin/activate` for Mac and Linux

## PyTest

Installation of `pytest` with `pip install pytest`.

## Playwright

Installation of Playwright`pip install playwright` and also `plyawright install` to load browsers for headed tests. 

## pytest.ini

Holds settings for PyTest.

We can use the one in PFS deleting unwanted entries.

## log folder

Folder to store `pytest.log` file for logging messages as defined in `pytest.ini`.

```
# for log file - pytest uses these whenever logger used
# boiler plate code that can be changed to suit

log_file = log/pytesting.log # customise location as required
log_file_level = INFO
log_file_format = %(asctime)s [%(levelname)8s] [%(name)s] %(message)s (%(filename)s:%(lineno)s)
log_file_date_format=%Y-%m-%d %H:%M:%S
```

In PFS, the logging location is `log` so we create this folder.

*For reference only:*

[https://docs.pytest.org/en/8.3.x/contents.html](https://docs.pytest.org/en/8.3.x/contents.html)

![customise-logging](../images/workshop/customise-logging.png)

## utils folder

Utility functions are stored in `utils`.

Some of these are used in PFS tests.

## config folder

Folder that holds `*.ini` files or other config files. We create a `config` folder.

This can be useful as an alternative to CLI arguments. We can add our options in the config.ini file to be retrieved in our tests using the `read_config.py` file. 

This is standard Python.


## results folder

We will need the `conftest.py` file to use the local plugin for CSV ouput and console formating.

We will need to `pip install rich pyboxen` for this.

Our custom CSV ouput files will go here based on the settings in the root `conftest.py` file, (near top of file), in the tests folder:

```
# ----- OUTPUT FILENAME AND LOCATION -----
report_date = datetime.now().strftime("%Y-%m-%d-%H-%M-%S")
# practically a GUID...
FILENAME = f"./results/report_{report_date}_{random.randint(1_000_000, 9_999_999)}.csv"
```

We will see later that using a filename like this means that we can load results into a DB by reading the filename to get report date and run_id, as well as all the test results. These three can form one row in the DB enabling auditing of test results all the way to the individual test level.

## reports folder

This is where we store our pytest-html reports, but we can choose any folder but we will use `reports` as in PFS.

We need to `pip install pytest-html`.

## htmlcov folder

We need to `pip install pytest-cov`.

Coverage report from pytest-cov can go here depending if we use `pytest --cov=htmlcov tests/`.

A `.coverage` report file is produced in the root of the project. 

## pytest-xdist

To speed up tests we `pip install pytest-xdist`.

## screenshots folder

If we are using some image, video and traceback Playwright features, we cann add a `screenshots` folder, (or any name we choose).

`test_08_download.py` uses the `screenshot` folder.

## Tests!

All our tests are stored in the `tests` folder.

We don't need to add `__init__.py` in this folder or subfolders but if we don't, we may have a test name collision if two tests have the same name.

## PFS

With all of these, we have replicated PFS, although we may choose to add Rich and Pyboxen for colorisation etc.

<br>