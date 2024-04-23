# The Pytest Cookbook - recipes with videos and repos

## Purpose of this book

To provide a range of ready congfigured PYTHON TEST FRAMEWORKS with a 'one step install', comprising of templates and references for developers to adapt to their own needs.

To provide curated resources of articles, videos and books that I have found useful.

Frameworks, apps and folders may well have additional README.md files to give more detailed instructions.

## Test Suites

These four are incremental, with each suite adding more functionality to the previous one:

- PyTest_00_MINIMAL - a basic src folder wired to PyTest with custom logging and pytest-sugar console formating.
- PyTest_01_PYTEST - as above but with a large number of ready made test templates demoing how to use PyTest along with templates for Mocking and Patching.
- PyTest_02_API_PLAYWRIGHT - as above with API testing and Playwright e2e/functional testing.
- PyTest_03_BDD - as above with Behavior Driven testing that enables the use of native English test requirement files to be wired to PyTest and Behave Framework. BDD enables all stakeholders to work on these 'feature' test files in plain English which are then translated to Python test code.
- PyTest_04_DB_TESTING - is a standalone test suite for testing database schemas such as foreigh kets, constraints, nullability etc. Uses SQLModel (SQLAlchemy + Pydantic)
- PyTest__05_DJANGO is its own unique testing suite built from a range of sources.
- PyTest_06_HYPOTHESIS is a standalone property based test suite that can provide templates and resources on how to use property based testing.


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