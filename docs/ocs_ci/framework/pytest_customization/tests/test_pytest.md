# Test Pytest

> Auto-generated documentation for [ocs_ci.framework.pytest_customization.tests.test_pytest](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/tests/test_pytest.py) module.

- [Ocs-ci](../../../../README.md#ocs-ci) / [Modules](../../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../../index.md#ocs-ci) / [Framework](../../index.md#framework) / [pytest customization](../index.md#pytest-customization) / [Tests](index.md#tests) / Test Pytest
    - [reset_config](#reset_config)
    - [test_config_parametrize](#test_config_parametrize)
    - [test_help_message](#test_help_message)
    - [test_pytest_works](#test_pytest_works)
    - [test_simple](#test_simple)

## reset_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/tests/test_pytest.py#L18)

```python
@fixture(autouse=True)
def reset_config():
```

## test_config_parametrize

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/tests/test_pytest.py#L62)

```python
def test_config_parametrize(testdir, tmpdir):
```

Parametrization via config values, use case described in
https://github.com/red-hat-storage/ocs-ci/pull/61#issuecomment-494866745

## test_help_message

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/tests/test_pytest.py#L27)

```python
def test_help_message(testdir):
```

Check that ``py.test --help`` output lists custom options of
ocscilib pytest plugin.

## test_pytest_works

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/tests/test_pytest.py#L23)

```python
def test_pytest_works():
```

## test_simple

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/tests/test_pytest.py#L45)

```python
def test_simple(testdir):
```

Make sure that  pytest itself is not broken by running very simple test.
