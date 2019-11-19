# CSV

> Auto-generated documentation for [ocs_ci.ocs.resources.csv](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/csv.py) module.

CSV related functionalities

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Ocs](../index.md#ocs) / [Resources](index.md#resources) / CSV
    - [CSV](#csv)
    - [get_csvs_start_with_prefix](#get_csvs_start_with_prefix)

## CSV

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/csv.py#L7)

```python
class CSV(OCP):
    def __init__(resource_name='', *args, **kwargs):
```

This class represent ClusterServiceVersion (CSV) and contains all related
methods we need to do with CSV.

#### See also

- [OCP](../ocp.md#ocp)

## get_csvs_start_with_prefix

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/csv.py#L28)

```python
def get_csvs_start_with_prefix(csv_prefix, namespace):
```

Get CSVs start with prefix

#### Arguments

- `csv_prefix` *str* - prefix from name
- `namespace` *str* - namespace of CSV

#### Returns

- `list` - found CSVs
