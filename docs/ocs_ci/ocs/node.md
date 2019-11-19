# Node

> Auto-generated documentation for [ocs_ci.ocs.node](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Node
    - [drain_nodes](#drain_nodes)
    - [get_node_objs](#get_node_objs)
    - [get_typed_nodes](#get_typed_nodes)
    - [get_typed_worker_nodes](#get_typed_worker_nodes)
    - [remove_nodes](#remove_nodes)
    - [schedule_nodes](#schedule_nodes)
    - [unschedule_nodes](#unschedule_nodes)
    - [wait_for_nodes_status](#wait_for_nodes_status)

## drain_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py#L136)

```python
def drain_nodes(node_names):
```

Drain nodes

#### Arguments

- `node_names` *list* - The names of the nodes

## get_node_objs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py#L12)

```python
def get_node_objs(node_names=None):
```

Get node objects by node names

#### Arguments

- `node_names` *list* - The node names to get their objects for.
    If None, will return all cluster nodes

#### Returns

- `list` - Cluster node OCP objects

## get_typed_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py#L36)

```python
def get_typed_nodes(node_type='worker', num_of_nodes=None):
```

Get cluster's nodes according to the node type (e.g. worker, master) and the
number of requested nodes from that type

#### Arguments

- `node_type` *str* - The node type (e.g. worker, master)
- `num_of_nodes` *int* - The number of nodes to be returned

#### Returns

- `list` - The nodes OCP instances

## get_typed_worker_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py#L153)

```python
def get_typed_worker_nodes(os_id='rhcos'):
```

Get worker nodes with specific OS

#### Arguments

- `os_id` *str* - OS type like rhcos, RHEL etc...

#### Returns

- `list` - list of worker nodes instances having specified os

## remove_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py#L171)

```python
def remove_nodes(nodes):
```

Remove the nodes from cluster

#### Arguments

- `nodes` *list* - list of node instances to remove from cluster

## schedule_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py#L121)

```python
def schedule_nodes(node_names):
```

Change nodes to be scheduled

#### Arguments

- `node_names` *list* - The names of the nodes

## unschedule_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py#L103)

```python
def unschedule_nodes(node_names):
```

Change nodes to be unscheduled

#### Arguments

- `node_names` *list* - The names of the nodes

## wait_for_nodes_status

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/node.py#L60)

```python
def wait_for_nodes_status(
    node_names=None,
    status=constants.NODE_READY,
    timeout=180,
):
```

Wait until all nodes are in the given status

#### Arguments

- `node_names` *list* - The node names to wait for to reached the desired state
    If None, will wait for all cluster nodes
- `status` *str* - The node status to wait for
    (e.g. 'Ready', 'NotReady', 'SchedulingDisabled')
- `timeout` *int* - The number in seconds to wait for the nodes to reach
    the status

#### Raises

- `ResourceWrongStatusException` - In case one or more nodes haven't
    reached the desired state
