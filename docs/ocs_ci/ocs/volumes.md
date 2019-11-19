# Volumes

> Auto-generated documentation for [ocs_ci.ocs.volumes](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/volumes.py) module.

A module which consists of kubevolume related operations

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Volumes
    - [CephRBDVolume](#cephrbdvolume)
        - [CephRBDVolume().create_cephblockpool](#cephrbdvolumecreate_cephblockpool)
    - [KubeVolume](#kubevolume)
    - [PVC](#pvc)
        - [PVC().create_pvc](#pvccreate_pvc)
    - [StorageClass](#storageclass)
        - [StorageClass().create_storageclass](#storageclasscreate_storageclass)

## CephRBDVolume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/volumes.py#L35)

```python
class CephRBDVolume(KubeVolume):
    def __init__(name=None, namespace='default'):
```

Class which contains Ceph RBD related functionality

#### Attributes

- `name` *str* - Name of the RBD volume
- `namepsace` *str* - Namespace to create RBD volume

#### See also

- [KubeVolume](#kubevolume)

### CephRBDVolume().create_cephblockpool

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/volumes.py#L58)

```python
def create_cephblockpool(
    cephblockpool_name_prefix='autotests-cephblockpool',
    failureDomain='host',
    replica_count='3',
):
```

Creates cephblock pool

#### Arguments

- `cephblockpool_name_prefix` *str* - Prefix given to cephblockpool
- `failureDomain` *str* - The failure domain across which the
                     replicas or chunks of data will be spread
- `replica_count` *int* - The number of copies of the data in the pool.

#### Returns

str : Name of the cephblockpool created

#### Raises

KeyError when error occured

#### Examples

create_cephblockpool(
    cephblockpool_name_prefix="autotests-blockpool",
    failureDomain="host",
    replica_count=3
)

## KubeVolume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/volumes.py#L19)

```python
class KubeVolume(object):
    def __init__(name, namespace):
```

Base class for cluster volumes

#### Attributes

- `name` *str* - Name of the RBD volume
- `namepsace` *str* - Namespace to create RBD volume

## PVC

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/volumes.py#L184)

```python
class PVC(KubeVolume):
    def __init__(name=None, namespace='default'):
```

Class which contains PVC related functionality

#### Attributes

- `name` *str* - Name of the PVC volume
- `namespace` *str* - Namespace to create PVC

#### See also

- [KubeVolume](#kubevolume)

### PVC().create_pvc

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/volumes.py#L205)

```python
def create_pvc(
    storageclass,
    accessmode='ReadWriteOnce',
    pvc_name_prefix='autotests-pvc',
    pvc_size=3,
):
```

Creates PVC using data provided

#### Arguments

- `storageclass` *str* - Name of storageclass to create PVC
- `accessmode` *str* - Access mode for PVC
- `pvc_name_prefix` *str* - Prefix given to PVC name
- `pvc_size` *int* - Size of PVC in Gb

#### Returns

- `str` - Name of the pvc created

#### Examples

create_pvc(
    storageclass,
    accessmode="ReadWriteOnce",
    pvc_size=3
)
create_pvc(
    storageclass,
    accessmode="ReadWriteOnce ReadOnlyMany",
    pvc_size=5
)

## StorageClass

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/volumes.py#L103)

```python
class StorageClass(KubeVolume):
    def __init__(name=None, namespace='default'):
```

Class which contains StorageClass related functionality

#### Attributes

- `name` *str* - Name of the RBD volume
- `namespace` *str* - Namespace to create RBD volume

#### See also

- [KubeVolume](#kubevolume)

### StorageClass().create_storageclass

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/volumes.py#L125)

```python
def create_storageclass(
    blockPool,
    sc_name_prefix='autotests-sc',
    allow_volume_expansion=True,
    reclaim_policy='Delete',
    fstype='xfs',
    clusterNamespace=framework.config.ENV_DATA['cluster_namespace'],
):
```

Creates storage class using data provided

#### Arguments

- `blockPool` *str* - Name of the block pool
- `sc_name_prefix` *str* - SC name will consist of this prefix and
                      random str.
- `allow_volume_expansion` *bool* - Either True or False
- `reclaim_policy` *str* - Reclaim Policy type. Either Retain,
                      Recycle or Delete
- `fstype` *str* - Filesystem type
- `clusterNamespace` *str* - Namespace where rook cluster exists

#### Returns

- `str` - Name of the storage class created

#### Examples

create_storageclass(
    blockPool,
    sc_name_prefix="autotests-sc",
    allow_volume_expansion=True,
    reclaim_policy="Delete",
    fstype="xfs"
    clusternamespace="openshift-storage",
)
