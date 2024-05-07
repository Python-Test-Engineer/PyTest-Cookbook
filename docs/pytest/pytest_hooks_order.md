# PyTest Hooks Order





![Flow chart!](../images/pytest-hooks.png "PyTest Hooks")

## Running `python -m pytest --debug` produces a `pytestdebug.log` with hook order.


![--debug!](../images/pytest-hooks--debug.png "PyTest Hooks")

from https://paragkamble.medium.com/understanding-hooks-in-pytest-892e91edbdb7#:~:text=These%20hooks%20use%20to%20perform,by%20decorating%20it%20with%20%40pytest.
```
root
└── pytest_cmdline_main
 ├── pytest_plugin_registered
 ├── pytest_configure
 │ └── pytest_plugin_registered
 ├── pytest_sessionstart
 │ ├── pytest_plugin_registered
 │ └── pytest_report_header
 ├── pytest_collection # this will need to be run first and be the wrapper
 │ ├── pytest_collectstart
 │ ├── pytest_make_collect_report
 │ │ ├── pytest_collect_file
 │ │ │ └── pytest_pycollect_makemodule # we can specify if our hooks fun first or last
 │ │ └── pytest_pycollect_makeitem
 │ │ └── pytest_generate_tests
 │ │ └── pytest_make_parametrize_id
 │ ├── pytest_collectreport
 │ ├── pytest_itemcollected
 │ ├── pytest_collection_modifyitems
 │ └── pytest_collection_finish
 │ └── pytest_report_collectionfinish
 ├── pytest_runtestloop
 │ └── pytest_runtest_protocol
 │ ├── pytest_runtest_logstart
 │ ├── pytest_runtest_setup
 │ │ └── pytest_fixture_setup
 │ ├── pytest_runtest_makereport
 │ ├── pytest_runtest_logreport
 │ │ └── pytest_report_teststatus
 │ ├── pytest_runtest_call
 │ │ └── pytest_pyfunc_call
 │ ├── pytest_runtest_teardown
 │ │ └── pytest_fixture_post_finalizer
 │ └── pytest_runtest_logfinish
 ├── pytest_sessionfinish
 │ └── pytest_terminal_summary
 └── pytest_unconfigure

```