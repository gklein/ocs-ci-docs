# TestConfig

> Auto-generated documentation for [ocs_ci.framework.tests.test_config](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py) module.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Framework](../index.md#framework) / [Tests](index.md#tests) / TestConfig
    - [TestConfig](#testconfig)
        - [TestConfig().reset_config](#testconfigreset_config)
        - [TestConfig().test_custom_conf](#testconfigtest_custom_conf)
        - [TestConfig().test_defaults](#testconfigtest_defaults)
        - [TestConfig().test_defaults_specific](#testconfigtest_defaults_specific)
        - [TestConfig().test_layered_conf](#testconfigtest_layered_conf)
    - [TestMergeDict](#testmergedict)
        - [TestMergeDict().test_merge_dict](#testmergedicttest_merge_dict)

## TestConfig

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py#L7)

```python
class TestConfig(object):
```

### TestConfig().reset_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py#L8)

```python
@fixture(autouse=True)
def reset_config():
```

### TestConfig().test_custom_conf

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py#L25)

```python
def test_custom_conf():
```

### TestConfig().test_defaults

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py#L12)

```python
def test_defaults():
```

### TestConfig().test_defaults_specific

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py#L18)

```python
def test_defaults_specific():
```

### TestConfig().test_layered_conf

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py#L36)

```python
def test_layered_conf():
```

## TestMergeDict

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py#L51)

```python
class TestMergeDict():
```

### TestMergeDict().test_merge_dict

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/tests/test_config.py#L52)

```python
def test_merge_dict():
```
