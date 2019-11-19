# Helpers

> Auto-generated documentation for [ocs_ci.utility.workloads.helpers](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/workloads/helpers.py) module.

Helper function for workloads to use

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Utility](../index.md#utility) / [Workloads](index.md#workloads) / Helpers
    - [find_distro](#find_distro)

## find_distro

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/workloads/helpers.py#L13)

```python
def find_distro(io_pod):
```

Find whats the os distro on pod

#### Arguments

- `io_pod` *Pod* - app pod object

#### Returns

- `distro` *str* - representing 'Debian' or 'RHEL' as of now
