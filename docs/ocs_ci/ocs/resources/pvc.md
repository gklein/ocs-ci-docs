# PVC

> Auto-generated documentation for [ocs_ci.ocs.resources.pvc](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py) module.

General PVC object

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Ocs](../index.md#ocs) / [Resources](index.md#resources) / PVC
    - [PVC](#pvc)
        - [PVC().backed_pv](#pvcbacked_pv)
        - [PVC().backed_pv_obj](#pvcbacked_pv_obj)
        - [PVC().backed_sc](#pvcbacked_sc)
        - [PVC().get_pvc_access_mode](#pvcget_pvc_access_mode)
        - [PVC().image_uuid](#pvcimage_uuid)
        - [PVC().reclaim_policy](#pvcreclaim_policy)
        - [PVC().resize_pvc](#pvcresize_pvc)
        - [PVC().size](#pvcsize)
        - [PVC().status](#pvcstatus)
    - [delete_pvcs](#delete_pvcs)
    - [get_all_pvc_objs](#get_all_pvc_objs)
    - [get_all_pvcs](#get_all_pvcs)
    - [get_deviceset_pvs](#get_deviceset_pvs)

## PVC

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L16)

```python
class PVC(OCS):
    def __init__(**kwargs):
```

A basic PersistentVolumeClaim kind resource

#### See also

- [OCS](ocs.md#ocs)

### PVC().backed_pv

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L50)

```python
@property
def backed_pv():
```

Returns the backed PV name of pvc_name in namespace

#### Returns

- `str` - PV name

### PVC().backed_pv_obj

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L60)

```python
@property
def backed_pv_obj():
```

Returns the backed PV object of pvc_name in namespace

#### Returns

- `OCS` - An OCS instance for PV

### PVC().backed_sc

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L103)

```python
@property
def backed_sc():
```

Returns the storage class of pvc object in namespace

#### Returns

- `str` - Storage class name

### PVC().get_pvc_access_mode

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L93)

```python
@property
def get_pvc_access_mode():
```

Function to get pvc access_mode

#### Returns

- `(str)` - The accessModes Value of pvc_obj

### PVC().image_uuid

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L79)

```python
@property
def image_uuid():
```

Fetch image uuid associated with PVC

#### Returns

- `str` - Image uuid associated with PVC

### PVC().reclaim_policy

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L113)

```python
@property
def reclaim_policy():
```

Returns the reclaim policy of pvc in namespace

#### Returns

- `str` - Reclaim policy Reclaim or Delete

### PVC().resize_pvc

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L132)

```python
def resize_pvc(new_size, verify=False):
```

Returns the PVC size pvc_name in namespace

#### Returns

- `bool` - True if operation succeeded, False otherwise

### PVC().size

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L29)

```python
@property
def size():
```

Returns the PVC size pvc_name in namespace

#### Returns

- `int` - PVC size

### PVC().status

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L40)

```python
@property
def status():
```

Returns the PVC status

#### Returns

- `str` - PVC status

## delete_pvcs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L146)

```python
def delete_pvcs(pvc_objs, concurrent=False):
```

Deletes list of the pvc objects

#### Arguments

- `pvc_objs` *list* - List of the pvc objects to be deleted
- `concurrent` *bool* - Determines if the delete operation should be
    executed with multiple thread in parallel

#### Returns

- `bool` - True if deletion is successful

## get_all_pvc_objs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L188)

```python
def get_all_pvc_objs(namespace=None, selector=None):
```

Gets all PVCs objects in given namespace

#### Arguments

- `namespace` *str* - Name of namespace
- `selector` *str* - The label selector to look for

#### Returns

- `list` - Instances of PVC

## get_all_pvcs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L168)

```python
def get_all_pvcs(namespace=None, selector=None):
```

Gets all pvc in given namespace

#### Arguments

- `namespace` *str* - Name of namespace
- `selector` *str* - The label selector to look for

#### Returns

- `dict` - Dict of all pvc in namespaces

## get_deviceset_pvs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pvc.py#L208)

```python
def get_deviceset_pvs():
```

Get the deviceset PVs

#### Returns

- `list` - the deviceset PVs OCS objects

#### Raises

- `AssertionError` - In case the deviceset PVCs are not found
