# Test Management

## Using the test name as meta data

If we name our tests with the following structure:

test_0001_api_description

We can programatically use the pytest_collection_modifyitems(items), where items is a list of tests, to extract out the following information:

- test id (0001).
- type of test, (api), which could be any 3 character code like dbm for database model, int for integrations, unt for unit etc
- we also get access to the nodeid and markers for each test with this hook.

This can be loaded into a database and then combined with the output CSVs that have:

- test id
- test name
-  any markers
- test node id which gives folder, parent folders up to tests folder
- test result
- test duration

Docstrings can also be extracted and added to the database.

##  Report name as test run information

Furthermore, as output test CSV files have the format of `report_2024-06-02-13-39-00_9496487.csv`, we can split the filename on '_'. giving us the date and time of the test from the second item. This should be globally unique as it gives the time to the second, but to ensure global uniqueness, a randon intger between, 1_000_000 and 9_999_999 is added.

We can also include the application version as well, i.e. `report_V061_2024-06-02-13-39-00_9496487.csv`, whee V061 would indicate a development sprint 67.

These files can then be digested and inserted into SQL tables enabling a full audit trail of tests over time and versions to be made.

This enable these data tables to be joined to create detailed test reporting. A sprint version number can also be added to create a history of tests by sprint.

Extending the database with test creators, creation date, test modifier and modification date, we can create audit trails of tests.

<br>

