# Reports

> Auto-generated documentation for [ocs_ci.framework.pytest_customization.reports](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/reports.py) module.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Framework](../index.md#framework) / [pytest customization](index.md#pytest-customization) / Reports
    - [pytest_html_results_table_header](#pytest_html_results_table_header)
    - [pytest_html_results_table_row](#pytest_html_results_table_row)
    - [pytest_runtest_makereport](#pytest_runtest_makereport)
    - [pytest_sessionfinish](#pytest_sessionfinish)

## pytest_html_results_table_header

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/reports.py#L8)

```python
@pytest.mark.optionalhook
def pytest_html_results_table_header(cells):
```

Add Description header to the table

## pytest_html_results_table_row

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/reports.py#L16)

```python
@pytest.mark.optionalhook
def pytest_html_results_table_row(report, cells):
```

Add content to the column Description

## pytest_runtest_makereport

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/reports.py#L27)

```python
@pytest.mark.hookwrapper
def pytest_runtest_makereport(item, call):
```

Add extra column( Log File) and link the log file location

## pytest_sessionfinish

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/reports.py#L44)

```python
def pytest_sessionfinish(session, exitstatus):
```

send email report
