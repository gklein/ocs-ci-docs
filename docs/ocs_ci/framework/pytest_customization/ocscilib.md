# Ocscilib

> Auto-generated documentation for [ocs_ci.framework.pytest_customization.ocscilib](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/ocscilib.py) module.

This is plugin for all the plugins/hooks related to OCS-CI and its
configuration.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Framework](../index.md#framework) / [pytest customization](index.md#pytest-customization) / Ocscilib
    - [pytest_addoption](#pytest_addoption)

The basic configuration is done in run_ocsci.py module casue we need to load
all the config before pytest run. This run_ocsci.py is just a wrapper for
pytest which proccess config and passes all params to pytest.

## pytest_addoption

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/ocscilib.py#L37)

```python
def pytest_addoption(parser):
```

Add necessary options to initialize OCS CI library.
