# Test Main

> Auto-generated documentation for [ocs_ci.framework.tests.test_main](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_main.py) module.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Framework](../index.md#framework) / [Tests](index.md#tests) / Test Main
    - [TestEntrypoint](#testentrypoint)
        - [TestEntrypoint().reset_config](#testentrypointreset_config)
        - [TestEntrypoint().test_config_passing](#testentrypointtest_config_passing)
        - [TestEntrypoint().test_help](#testentrypointtest_help)
        - [TestEntrypoint().test_multi_config_passing](#testentrypointtest_multi_config_passing)
        - [TestEntrypoint().test_no_args](#testentrypointtest_no_args)

## TestEntrypoint

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_main.py#L14)

```python
class TestEntrypoint(object):
```

### TestEntrypoint().reset_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_main.py#L15)

```python
@fixture(autouse=True)
def reset_config():
```

### TestEntrypoint().test_config_passing

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_main.py#L35)

```python
@mock.patch('ocs_ci.framework.main.pytest.main')
@mock.patch.object(config, 'update')
def test_config_passing(config_update, pytest_main, testdir):
```

### TestEntrypoint().test_help

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_main.py#L19)

```python
def test_help():
```

### TestEntrypoint().test_multi_config_passing

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_main.py#L52)

```python
@mock.patch('ocs_ci.framework.main.pytest.main')
@mock.patch.object(config, 'update')
def test_multi_config_passing(config_update, pytest_main, testdir):
```

### TestEntrypoint().test_no_args

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_main.py#L29)

```python
@mock.patch('ocs_ci.framework.main.pytest.main')
@mock.patch.object(config, 'update')
def test_no_args(config_update, pytest_main, testdir):
```
