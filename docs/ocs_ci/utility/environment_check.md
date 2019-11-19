# Environment Check

> Auto-generated documentation for [ocs_ci.utility.environment_check](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/environment_check.py) module.

Util for environment check before and after test to compare and find stale
leftovers

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / Environment Check
    - [assign_get_values](#assign_get_values)
    - [compare_dicts](#compare_dicts)
    - [get_environment_status](#get_environment_status)
    - [get_status_after_execution](#get_status_after_execution)
    - [get_status_before_execution](#get_status_before_execution)

## assign_get_values

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/environment_check.py#L76)

```python
def assign_get_values(
    env_status_dict,
    key,
    kind=None,
    exclude_namespaces=('openshift-marketplace'),
):
```

Assigning kind status into env_status_dict

#### Arguments

- `env_status_dict` *dict* - Dictionary which is
    copy.deepcopy(ENV_STATUS_DICT)
- `key` *str* - Name of the resource
kind (OCP obj): OCP object for a resource
exclude_namespaces (list or tuple): List/tuple of namespaces to ignore

## compare_dicts

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/environment_check.py#L36)

```python
def compare_dicts(before, after):
```

Comparing 2 dicts and providing diff list of [added items, removed items]

#### Arguments

- `before` *dict* - Dictionary before execution
- `after` *dict* - Dictionary after execution

#### Returns

- `list` - List of 2 lists - ('added' and 'removed' are lists)

## get_environment_status

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/environment_check.py#L99)

```python
def get_environment_status(env_dict):
```

Get the environment status per kind in KINDS and save it in a dictionary

#### Arguments

- `env_dict` *dict* - Dictionary that is a copy.deepcopy(ENV_STATUS_DICT)

## get_status_after_execution

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/environment_check.py#L118)

```python
def get_status_after_execution():
```

Set the environment status and assign it into ENV_STATUS_PRE dictionary.
In addition compare the dict before the execution and after using DeepDiff

#### Raises

- `ResourceLeftoversException` - In case there are leftovers in the
   environment after the execution

## get_status_before_execution

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/environment_check.py#L111)

```python
def get_status_before_execution():
```

Set the environment status and assign it into ENV_STATUS_PRE dictionary
