# WorkLoad

> Auto-generated documentation for [ocs_ci.ocs.workload](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/workload.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / WorkLoad
    - [WorkLoad](#workload)
        - [WorkLoad().run](#workloadrun)
        - [WorkLoad().setup](#workloadsetup)

## WorkLoad

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/workload.py#L9)

```python
class WorkLoad(object):
    def __init__(
        name=None,
        path=None,
        work_load=None,
        storage_type='fs',
        pod=None,
        jobs=1,
    ):
```

### WorkLoad().run

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/workload.py#L69)

```python
def run(**conf):
```

Perform work_load_mod.run in order to run actual io.
Every workload module should implement run() function so that we can
invoke <workload_module>.run() to run IOs.

#### Arguments

- `**conf` *dict* - Run configuration a.k.a parameters for workload
    io runs

#### Returns

- `result` *Future* - Returns a concurrent.future object

### WorkLoad().setup

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/workload.py#L51)

```python
def setup(**setup_conf):
```

Perform work_load_mod.setup() to setup the workload.
Every workload module should implement setup() method so that
respective <workload_module>.setup() function can be called from here

#### Arguments

- `setup_conf` *dict* - Work load setup configuration, varies from
    workload to workload. Refer constants.TEMPLATE_WORKLOAD_DIR
    for various available workloads

#### Returns

- `bool` - True if setup is success else False
