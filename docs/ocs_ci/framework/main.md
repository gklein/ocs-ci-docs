# Main

> Auto-generated documentation for [ocs_ci.framework.main](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/main.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Framework](index.md#framework) / Main
    - [check_config_requirements](#check_config_requirements)
    - [init_ocsci_conf](#init_ocsci_conf)
    - [main](#main)

## check_config_requirements

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/main.py#L13)

```python
def check_config_requirements():
```

Checking if all required parameters were passed

#### Raises

- `MissingRequiredConfigKeyError` - In case of some required parameter is
    not defined.

## init_ocsci_conf

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/main.py#L38)

```python
def init_ocsci_conf(arguments=None):
```

Update the config object with any files passed via the CLI

#### Arguments

- `arguments` *list* - Arguments for pytest execution

## main

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/main.py#L71)

```python
def main(arguments):
```
