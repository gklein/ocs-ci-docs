# RipSaw

> Auto-generated documentation for [ocs_ci.ocs.ripsaw](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ripsaw.py) module.

RipSaw Class to run various workloads and scale tests

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / RipSaw
    - [RipSaw](#ripsaw)
        - [RipSaw().apply_crd](#ripsawapply_crd)
        - [RipSaw().cleanup](#ripsawcleanup)
        - [RipSaw().setup_postgresql](#ripsawsetup_postgresql)

## RipSaw

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ripsaw.py#L20)

```python
class RipSaw(object):
    def __init__(**kwargs):
```

Workload operation using RipSaw

### RipSaw().apply_crd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ripsaw.py#L80)

```python
def apply_crd(crd):
```

Apply the CRD

#### Arguments

- `crd` *str* - Name of file to apply

### RipSaw().cleanup

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ripsaw.py#L123)

```python
def cleanup():
```

### RipSaw().setup_postgresql

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ripsaw.py#L93)

```python
def setup_postgresql():
```

Deploy postgres sql server
