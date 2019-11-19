# Jenkins

> Auto-generated documentation for [ocs_ci.utility.workloads.jenkins](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/workloads/jenkins.py) module.

This module implements all the functionalities required for setting up and
running "Jenkins" like workloads on the pods.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Utility](../index.md#utility) / [Workloads](index.md#workloads) / Jenkins
    - [run](#run)
    - [setup](#setup)

This module implements few functions
setup(): for setting up git utility on the pod and any necessary
    environmental params.
run(): for running 'git clone' on pod to simulate a working environment for
    a developer

Note: The above mentioned functions will be invoked from Workload.setup()
and Workload.run() methods along with user provided parameters.

## run

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/workloads/jenkins.py#L45)

```python
def run(**kwargs):
```

Run git clone

#### Returns

- `str` - result of command

## setup

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/workloads/jenkins.py#L20)

```python
def setup(**kwargs):
```

setup git workload

#### Arguments

- `**kwargs` *dict* - git setup configuration.
    The only argument present in kwargs is 'pod' on which we
    want to setup

#### Returns

- `bool` - True if setup succeeds else False
