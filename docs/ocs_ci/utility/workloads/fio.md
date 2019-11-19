# Fio

> Auto-generated documentation for [ocs_ci.utility.workloads.fio](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/workloads/fio.py) module.

This module implements all the functionalities required for setting up and
running Fio workloads on the pods.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Utility](../index.md#utility) / [Workloads](index.md#workloads) / Fio
    - [run](#run)
    - [setup](#setup)

This module implements few functions
setup(): for setting up fio utility on the pod and any necessary
    environmental params.
run(): for running fio on pod on specified mount point

Note: The above mentioned functions will be invoked from Workload.setup()
and Workload.run() methods along with user provided parameters.

## run

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/workloads/fio.py#L45)

```python
def run(**kwargs):
```

Run fio with params from kwargs.
Default parameter list can be found in
templates/workloads/fio/workload_io.yaml and user can update the
dict as per the requirement.

#### Arguments

- `kwargs` *dict* - IO params for fio

Result:
    result of command

## setup

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/workloads/fio.py#L19)

```python
def setup(**kwargs):
```

setup fio workload

#### Arguments

- `**kwargs` *dict* - fio setup configuration.
    At this point in time only argument present in kwargs will be
    'pod' on which we want to setup. In future if we move to
    containerized fio then pod.yaml will be presented in kwargs.

#### Returns

- `bool` - True if setup succeeds else False
