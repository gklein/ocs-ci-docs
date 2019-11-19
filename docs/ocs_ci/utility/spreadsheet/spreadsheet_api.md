# Spreadsheet Api

> Auto-generated documentation for [ocs_ci.utility.spreadsheet.spreadsheet_api](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/spreadsheet/spreadsheet_api.py) module.

API module to interact with Google spreadsheets
In order to create a new spreadsheet, share the spreadsheet with the
'client_email' in your credentials json file with write permissions.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Utility](../index.md#utility) / [Spreadsheet](index.md#spreadsheet) / Spreadsheet Api
    - [GoogleSpreadSheetAPI](#googlespreadsheetapi)
        - [GoogleSpreadSheetAPI().get_cell_value](#googlespreadsheetapiget_cell_value)
        - [GoogleSpreadSheetAPI().insert_row](#googlespreadsheetapiinsert_row)
        - [GoogleSpreadSheetAPI().print_sheet](#googlespreadsheetapiprint_sheet)
        - [GoogleSpreadSheetAPI().update_sheet](#googlespreadsheetapiupdate_sheet)

## GoogleSpreadSheetAPI

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/spreadsheet/spreadsheet_api.py#L14)

```python
class GoogleSpreadSheetAPI(object):
    def __init__(sheet_name, sheet_index):
```

A class to interact with Google Spreadsheet

### GoogleSpreadSheetAPI().get_cell_value

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/spreadsheet/spreadsheet_api.py#L41)

```python
def get_cell_value(row, col):
```

### GoogleSpreadSheetAPI().insert_row

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/spreadsheet/spreadsheet_api.py#L44)

```python
def insert_row(value, row_index=2):
```

### GoogleSpreadSheetAPI().print_sheet

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/spreadsheet/spreadsheet_api.py#L37)

```python
def print_sheet():
```

### GoogleSpreadSheetAPI().update_sheet

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/spreadsheet/spreadsheet_api.py#L31)

```python
def update_sheet(row, col, value):
```

Updates a row:col in a given spreadsheet
