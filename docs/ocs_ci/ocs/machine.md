# Machine

> Auto-generated documentation for [ocs_ci.ocs.machine](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Machine
    - [add_capacity](#add_capacity)
    - [add_node](#add_node)
    - [delete_machine](#delete_machine)
    - [delete_machine_and_check_state_of_new_spinned_machine](#delete_machine_and_check_state_of_new_spinned_machine)
    - [get_machine_objs](#get_machine_objs)
    - [get_machine_type](#get_machine_type)
    - [get_machines](#get_machines)
    - [get_machinesets](#get_machinesets)
    - [get_replica_count](#get_replica_count)
    - [get_storage_cluster](#get_storage_cluster)

## add_capacity

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L171)

```python
def add_capacity(
    count,
    storagecluster_name,
    namespace=defaults.ROOK_CLUSTER_NAMESPACE,
):
```

Add capacity to the cluster

#### Arguments

- `storagecluster_name` *str* - Name of a storage cluster
- `count` *int* - Count of osds to add, for ex: if total count of osds is 3, it will add 3 osds more

#### Returns

- `bool` - True if commands executes successfully

## add_node

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L155)

```python
def add_node(machine_set, count):
```

Add new node to the cluster

#### Arguments

- `machine_set` *str* - Name of a machine set to get increase replica count
- `count` *int* - Count to increase

#### Returns

- `bool` - True if commands executes successfully

## delete_machine

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L53)

```python
def delete_machine(machine_name):
```

Deletes a machine

#### Arguments

- `machine_name` *str* - Name of the machine you want to delete

#### Raises

- `CommandFailed` - In case yaml_file and resource_name wasn't provided

## delete_machine_and_check_state_of_new_spinned_machine

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L91)

```python
def delete_machine_and_check_state_of_new_spinned_machine(machine_name):
```

Deletes a machine and checks the state of the newly spinned
machine

#### Arguments

- `machine_name` *str* - Name of the machine you want to delete

#### Returns

- `bool` - True in case of success, False otherwise

## get_machine_objs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L10)

```python
def get_machine_objs(machine_names=None):
```

Get machine objects by machine names

#### Arguments

- `machine_names` *list* - The machine names to get their objects
If None, will return all cluster machines

#### Returns

- `list` - Cluster machine OCS objects

## get_machine_type

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L70)

```python
def get_machine_type(machine_name):
```

Get the machine type (e.g. worker, master)

#### Arguments

- `machine_name` *str* - Name of the machine

#### Returns

- `str` - Type of the machine

## get_machines

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L35)

```python
def get_machines(machine_type=constants.WORKER_MACHINE):
```

Get cluster's machines according to the machine type (e.g. worker, master)

#### Arguments

- `machine_type` *str* - The machine type (e.g. worker, master)

#### Returns

- `list` - The nodes OCP instances

## get_machinesets

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L124)

```python
def get_machinesets():
```

Get machine sets

#### Returns

- `machine_sets` *list* - list of machine sets

## get_replica_count

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L141)

```python
def get_replica_count(machine_set):
```

Get replica count of a machine set

#### Arguments

- `machine_set` *str* - Name of a machine set to get replica count

#### Returns

replica count (int): replica count of a machine set

## get_storage_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/machine.py#L191)

```python
def get_storage_cluster(namespace=defaults.ROOK_CLUSTER_NAMESPACE):
```

Get storage cluster name

#### Arguments

- `namespace` *str* - Namespace of the resource

#### Returns

- `str` - Storage cluster name
