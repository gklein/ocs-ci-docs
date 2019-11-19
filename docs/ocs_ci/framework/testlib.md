# Testlib

> Auto-generated documentation for [ocs_ci.framework.testlib](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/testlib.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Framework](index.md#framework) / Testlib
    - [BaseTest](#basetest)
    - [E2ETest](#e2etest)
    - [EcosystemTest](#ecosystemtest)
    - [ManageTest](#managetest)

## BaseTest

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/testlib.py#L4)

```python
pytest.mark.usefixtures('run_io_in_background', 'environment_checker')
class BaseTest():
```

Base test class for our testing.
If some functionality/property needs to be implemented in all test classes
here is the place to put your code.

## E2ETest

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/testlib.py#L16)

```python
e2e
class E2ETest(BaseTest):
```

Base class for E2E team

#### See also

- [BaseTest](#basetest)

## EcosystemTest

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/testlib.py#L32)

```python
ecosystem
class EcosystemTest(BaseTest):
```

Base class for E2E team

#### See also

- [BaseTest](#basetest)

## ManageTest

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/testlib.py#L24)

```python
manage
class ManageTest(BaseTest):
```

Base class for E2E team

#### See also

- [BaseTest](#basetest)
