# OCS

> Auto-generated documentation for [ocs_ci.ocs.resources.ocs](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py) module.

General OCS object

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Ocs](../index.md#ocs) / [Resources](index.md#resources) / OCS
    - [OCS](#ocs)
        - [OCS().add_label](#ocsadd_label)
        - [OCS().api_version](#ocsapi_version)
        - [OCS().apply](#ocsapply)
        - [OCS().create](#ocscreate)
        - [OCS().delete](#ocsdelete)
        - [OCS().delete_temp_yaml_file](#ocsdelete_temp_yaml_file)
        - [OCS().describe](#ocsdescribe)
        - [OCS().get](#ocsget)
        - [OCS().is_deleted](#ocsis_deleted)
        - [OCS().kind](#ocskind)
        - [OCS().name](#ocsname)
        - [OCS().namespace](#ocsnamespace)
        - [OCS().reload](#ocsreload)
    - [ocs_install_verification](#ocs_install_verification)

## OCS

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L20)

```python
class OCS(object):
    def __init__(**kwargs):
```

Base OCSClass

### OCS().add_label

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L139)

```python
def add_label(label):
```

Addss a new label

#### Arguments

- `label` *str* - New label to be assigned for this pod
    - `E.g` - "label=app='rook-ceph-mds'"

### OCS().api_version

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L59)

```python
@property
def api_version():
```

### OCS().apply

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L131)

```python
def apply(**data):
```

### OCS().create

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L97)

```python
def create(do_reload=True):
```

### OCS().delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L105)

```python
def delete(wait=True, force=False):
```

Delete the OCS object if its not already deleted
(using the internal is_deleted flag)

#### Arguments

- `wait` *bool* - Wait for object to be deleted
- `force` *bool* - Force delete object

#### Returns

- `bool` - True if deleted, False otherwise

### OCS().delete_temp_yaml_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L151)

```python
def delete_temp_yaml_file():
```

### OCS().describe

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L94)

```python
def describe():
```

### OCS().get

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L89)

```python
def get(out_yaml_format=True):
```

### OCS().is_deleted

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L75)

```python
@property
def is_deleted():
```

### OCS().kind

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L63)

```python
@property
def kind():
```

### OCS().name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L71)

```python
@property
def name():
```

### OCS().namespace

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L67)

```python
@property
def namespace():
```

### OCS().reload

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L79)

```python
def reload():
```

Reloading the OCS instance with the new information from its actual
data.
After creating a resource from a yaml file, the actual yaml file is
being changed and more information about the resource is added.

## ocs_install_verification

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/ocs.py#L155)

```python
def ocs_install_verification(timeout=600):
```

Perform steps necessary to verify a successful OCS installation

#### Arguments

- `timeout` *int* - Number of seconds for timeout which will be used in the
    checks used in this function.
