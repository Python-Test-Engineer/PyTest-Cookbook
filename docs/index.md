# The Pytest Cookbook - *recipes with videos and repos*

## Purpose of this book 

To provide a range of ready congfigured PYTHON TEST FRAMEWORKS with a 'one step install', comprising of templates and references for developers to adapt to their own needs.

To provide curated resources of articles, videos and books that I have found useful.

The premise is that if a developer has an easy to set up test suite with example tests, combined with links to video and text resources, they can readily adapt the test suites as needed without having to set them up and coonfigure them.

## How best to use

The repo has all the test suites rather than individual repos.

Download or git clone from [repo](https://github.com/Python-Test-Engineer/PYTHON-TEST-FRAMEWORK) and cd into the desired test suite.

Each test suite has a README.md and there are more details and information there as necessary. For Playwright you will neeed to run `playwright install` after Playwright is installed to load browsers.

For prettier console output Rich and PyBoxen, built on Rich, are used.

There will be links to any relevant YT videos I have made and the channel link for all the videos is [here](https://www.youtube.com/playlist?list=PLsszRSbzjyvkincV5XUzF9BeGsckrjb74).

Create a virtual environment and run `pip install -r requiements.txt`.

Run PyTest as a module preferably `python -m pytest` with arguments as necessary.

## Test Suites

*See the README.md in root of each Test Suite for detailed and up to date set up instructions.*

These four are incremental, with each suite adding more functionality to the previous one:

- PyTest_00_MINIMAL - a basic src folder wired to PyTest with custom logging and pytest-sugar console formating.
- PyTest_01_PYTEST - as above but with a large number of ready made test templates demoing how to use PyTest along with templates for Mocking and Patching.
- PyTest_02_API - as above with API testing and Playwright e2e/functional testing.
- PyTest_03_BDD - as above with Behavior Driven testing that enables the use of native English test requirement files to be wired to PyTest and Behave Framework. BDD enables all stakeholders to work on these 'feature' test files in plain English which are then translated to Python test code.

These are self-contained Test Suites:

- PyTest_04_DB_TESTING - is a standalone test suite for testing database schemas such as foreigh keys, constraints, nullability etc. Uses SQLModel (SQLAlchemy + Pydantic) to inspect DB. Uses SQLite as test DB and this has some restricted schema information but there are tests for thes.
- PyTest_05_DJANGO is its own unique testing suite built from a range of sources. 
- PyTest_06_HYPOTHESIS is a standalone property based test suite that can provide templates and resources on how to use property based testing. It can be thought of as very extensive parameter based testing to test edge cases and hone in on them.
- PyTest_07_PLUGIN - this is a template PyTest plugin project for adaptation.
- PyTest_08_HOOKS - a small project outputing information on hooks and what they provide.
- PyTest_09_CLI - testing a Typer CLI project.
- PyTest_10_CI_CD - a CI/CD example to show how we can use GitHub actions to test our code base on multiple Python versions and OS. May be replaced with TOX.


## Installation

- Download the main repo and navigate to required TEST_SUITE. The Github repo for all these TEST_SUITES is [here](https://github.com/Python-Test-Engineer/PYTHON-TEST-FRAMEWORK){target="_blank"}.
- Follow install instructions in README.md file of test suite.

## YouTube Videos

These are available [here](https://www.youtube.com/playlist?list=PLsszRSbzjyvkincV5XUzF9BeGsckrjb74){target="_blank"}.


## TODO

Django Tests

- https://www.photondesigner.com/articles/unit-tests-factory-boy-faker?ref=yt-unit-tests-factory-boy-faker

Testing middleware with `override_settings`

- https://www.youtube.com/watch?v=TTEEr4N-lKw


Add use of dynamically adding markers
import pytest

def pytest_collection_modifyitems(items):
    for item in items:
        if "model" in item.name:
            item.add_marker(pytest.mark.model)
        if "model_structure" in item.name:
            item.add_marker(pytest.mark.model_structure)
        if "unit" in item.name:
            item.add_marker(pytest.mark.unit)
        if "unit_schema" in item.name:
            item.add_marker(pytest.mark.unit_schema)