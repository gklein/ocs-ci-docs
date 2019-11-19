# Cluster

> Auto-generated documentation for [ocs_ci.ocs.cluster](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py) module.

A module for all rook functionalities and abstractions.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Cluster
    - [CephCluster](#cephcluster)
        - [CephCluster().check_ceph_pool_used_space](#cephclustercheck_ceph_pool_used_space)
        - [CephCluster().cluster_health_check](#cephclustercluster_health_check)
        - [CephCluster().cluster_name](#cephclustercluster_name)
        - [CephCluster().create_user](#cephclustercreate_user)
        - [CephCluster().get_admin_key](#cephclusterget_admin_key)
        - [CephCluster().get_mons_from_cluster](#cephclusterget_mons_from_cluster)
        - [CephCluster().get_user_key](#cephclusterget_user_key)
        - [CephCluster().is_health_ok](#cephclusteris_health_ok)
        - [CephCluster().mds_change_count](#cephclustermds_change_count)
        - [CephCluster().mds_health_check](#cephclustermds_health_check)
        - [CephCluster().mon_change_count](#cephclustermon_change_count)
        - [CephCluster().mon_health_check](#cephclustermon_health_check)
        - [CephCluster().namespace](#cephclusternamespace)
        - [CephCluster().pods](#cephclusterpods)
        - [CephCluster().remove_mon_from_cluster](#cephclusterremove_mon_from_cluster)
        - [CephCluster().scan_cluster](#cephclusterscan_cluster)
        - [CephCluster.set_port](#cephclusterset_port)
    - [validate_cluster_on_pvc](#validate_cluster_on_pvc)

This module has rook related classes, support for functionalities to work with
rook cluster. This works with assumptions that an OCP cluster is already
functional and proper configurations are made for interaction.

## CephCluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L29)

```python
class CephCluster(object):
    def __init__():
```

Handles all cluster related operations from ceph perspective

This class has depiction of ceph cluster. Contains references to
pod objects which represents ceph cluster entities.

#### Attributes

pods (list) : A list of  ceph cluster related pods
- `cluster_name` *str* - Name of ceph cluster
- `namespace` *str* - openshift Namespace where this cluster lives

### CephCluster().check_ceph_pool_used_space

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L407)

```python
@retry(UnexpectedBehaviour, tries=20, delay=10, backoff=1)
def check_ceph_pool_used_space(cbp_name):
```

Check for the used space of a pool in cluster

Returns:
   used_in_gb (float): Amount of used space in pool (in GBs)

Raises:
   UnexpectedBehaviour: If used size keeps varying in Ceph status

### CephCluster().cluster_health_check

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L185)

```python
def cluster_health_check(timeout=None):
```

Check overall cluster health.
Relying on health reported by CephCluster.get()

#### Arguments

- `timeout` *int* - in seconds. By default timeout value will be scaled
    based on number of ceph pods in the cluster. This is just a
    crude number. Its been observed that as the number of pods
    increases it takes more time for cluster's HEALTH_OK.

#### Returns

- `bool` - True if "HEALTH_OK"  else False

#### Raises

- `CephHealthException` - if cluster is not healthy

### CephCluster().cluster_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L110)

```python
@property
def cluster_name():
```

### CephCluster().create_user

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L356)

```python
def create_user(username, caps):
```

Create a ceph user in the cluster

#### Arguments

- `username` *str* - ex client.user1
- `caps` *str* - ceph caps ex: mon 'allow r' osd 'allow rw'

#### Returns

return value of get_user_key()

### CephCluster().get_admin_key

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L333)

```python
def get_admin_key():
```

#### Returns

- `adminkey` *str* - base64 encoded key

### CephCluster().get_mons_from_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L374)

```python
def get_mons_from_cluster():
```

Getting the list of mons from the cluster

#### Returns

- `available_mon` *list* - Returns the mons from the cluster

### CephCluster().get_user_key

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L340)

```python
def get_user_key(user):
```

#### Arguments

- `user` *str* - ceph username ex: client.user1

#### Returns

- `key` *str* - base64 encoded user key

### CephCluster().is_health_ok

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L177)

```python
def is_health_ok():
```

#### Returns

- `bool` - True if "HEALTH_OK" else False

### CephCluster().mds_change_count

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L292)

```python
def mds_change_count(new_count):
```

Change mds count in the cluster

#### Arguments

- `new_count(int)` - Absolute number of active mdss required

### CephCluster().mds_health_check

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L310)

```python
def mds_health_check(count):
```

MDS health check based on pod count

#### Arguments

- `count` *int* - number of pods expected

#### Raises

- `MDACountException` - if pod count doesn't match

### CephCluster().mon_change_count

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L241)

```python
def mon_change_count(new_count):
```

Change mon count in the cluster

#### Arguments

- `new_count(int)` - Absolute number of mons required

### CephCluster().mon_health_check

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L257)

```python
def mon_health_check(count):
```

Mon health check based on pod count

#### Arguments

- `count` *int* - Expected number of mon pods

#### Raises

- `MonCountException` - if mon pod count doesn't match

### CephCluster().namespace

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L114)

```python
@property
def namespace():
```

### CephCluster().pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L118)

```python
@property
def pods():
```

### CephCluster().remove_mon_from_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L388)

```python
def remove_mon_from_cluster():
```

Removing the mon pod from deployment

#### Returns

- `remove_mon(bool)` - True if removal of mon is successful, False otherwise

### CephCluster().scan_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L122)

```python
def scan_cluster():
```

Get accurate info on current state of pods

### CephCluster.set_port

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L157)

```python
@staticmethod
def set_port(pod):
```

Set port attribute on pod.
port attribute for mon is required for secrets and this attrib
is not a member for original pod class.

#### Arguments

- `pod(Pod)` - Pod object without 'port' attribute

#### Returns

- `pod(Pod)` - A modified pod object with 'port' attribute set

## validate_cluster_on_pvc

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/cluster.py#L431)

```python
def validate_cluster_on_pvc():
```

Validate creation of PVCs for MON and OSD pods.
Also validate that those PVCs are attached to the OCS pods

#### Raises

- `AssertionError` - If PVC is not mounted on one or more OCS pods
