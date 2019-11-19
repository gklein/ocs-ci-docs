# Openstack

> Auto-generated documentation for [ocs_ci.ocs.openstack](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Openstack
    - [CephVMNode](#cephvmnode)
        - [CephVMNode().attach_floating_ip](#cephvmnodeattach_floating_ip)
        - [CephVMNode().create_node](#cephvmnodecreate_node)
        - [CephVMNode().destroy_node](#cephvmnodedestroy_node)
        - [CephVMNode().destroy_volume](#cephvmnodedestroy_volume)
        - [CephVMNode().get_driver](#cephvmnodeget_driver)
        - [CephVMNode().get_private_ip](#cephvmnodeget_private_ip)
        - [CephVMNode().get_volume](#cephvmnodeget_volume)
    - [GetIPError](#getiperror)
    - [InvalidHostName](#invalidhostname)
    - [NodeErrorState](#nodeerrorstate)

## CephVMNode

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L45)

```python
class CephVMNode(object):
    def __init__(**kw):
```

### CephVMNode().attach_floating_ip

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L247)

```python
def attach_floating_ip(timeout=120):
```

### CephVMNode().create_node

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L80)

```python
def create_node(**kw):
```

### CephVMNode().destroy_node

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L225)

```python
def destroy_node():
```

Relies on the fact that names **should be** unique. Along the chain we
prevent non-unique names to be used/added.
TODO: raise an exception if more than one node is matched to the name, that
can be propagated back to the client.

### CephVMNode().destroy_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L239)

```python
def destroy_volume(name):
```

### CephVMNode().get_driver

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L68)

```python
def get_driver(**kw):
```

### CephVMNode().get_private_ip

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L208)

```python
def get_private_ip():
```

Workaround. self.node.private_ips returns empty list.

### CephVMNode().get_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L216)

```python
def get_volume(name):
```

Return libcloud.compute.base.StorageVolume

## GetIPError

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L41)

```python
class GetIPError(Exception):
```

## InvalidHostName

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L33)

```python
class InvalidHostName(Exception):
```

## NodeErrorState

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openstack.py#L37)

```python
class NodeErrorState(Exception):
```
