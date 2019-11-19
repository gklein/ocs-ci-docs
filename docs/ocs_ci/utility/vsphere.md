# VSPHERE

> Auto-generated documentation for [ocs_ci.utility.vsphere](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py) module.

This module contains the vSphere related methods

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / VSPHERE
    - [VSPHERE](#vsphere)
        - [VSPHERE().add_disk](#vsphereadd_disk)
        - [VSPHERE().add_disks](#vsphereadd_disks)
        - [VSPHERE().get_all_vms_in_pool](#vsphereget_all_vms_in_pool)
        - [VSPHERE().get_cluster](#vsphereget_cluster)
        - [VSPHERE().get_content](#vsphereget_content)
        - [VSPHERE().get_controller_for_adding_disk](#vsphereget_controller_for_adding_disk)
        - [VSPHERE().get_controllers](#vsphereget_controllers)
        - [VSPHERE().get_dc](#vsphereget_dc)
        - [VSPHERE().get_pool](#vsphereget_pool)
        - [VSPHERE().get_search_index](#vsphereget_search_index)
        - [VSPHERE().get_unit_number](#vsphereget_unit_number)
        - [VSPHERE().get_vm_by_ip](#vsphereget_vm_by_ip)
        - [VSPHERE().get_vm_in_pool_by_name](#vsphereget_vm_in_pool_by_name)

## VSPHERE

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L18)

```python
class VSPHERE(object):
    def __init__(host, user, password, port=443):
```

wrapper for vSphere

### VSPHERE().add_disk

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L244)

```python
def add_disk(vm, size, disk_type='thin'):
```

Attaches disk to VM

#### Arguments

- `vm` *vim.VirtualMachine* - VM instance
size (int) : size of disk in GB
disk_type (str) : disk type

### VSPHERE().add_disks

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L278)

```python
def add_disks(num_disks, vm, size, disk_type='thin'):
```

Adds multiple disks to the VM

#### Arguments

- `num_disks` - number of disks to add
- `vm` *vim.VirtualMachine* - VM instance
size (int) : size of disk in GB
disk_type (str) : disk type

### VSPHERE().get_all_vms_in_pool

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L153)

```python
def get_all_vms_in_pool(name, dc, cluster):
```

Gets all VM's in Resource pool

#### Arguments

- `name` *str* - Resource pool name
- `dc` *str* - Datacenter name
- `cluster` *str* - Cluster name

#### Returns

- `list` - VM instances (vim.VirtualMachine)

### VSPHERE().get_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L119)

```python
def get_cluster(name, dc):
```

Gets the cluster

#### Arguments

- `name` *str* - Cluster name
- `dc` *str* - Datacenter name

#### Returns

- `vim.ClusterComputeResource` - Cluster instance

### VSPHERE().get_content

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L67)

```python
@property
def get_content():
```

Retrieves the content

#### Returns

- `vim.ServiceInstanceContent` - Service Instance Content for Host

### VSPHERE().get_controller_for_adding_disk

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L204)

```python
def get_controller_for_adding_disk(vm):
```

Gets the controller for adding disk

#### Arguments

- `vm` *vim.VirtualMachine* - VM instance

#### Returns

controller instance

### VSPHERE().get_controllers

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L188)

```python
def get_controllers(vm):
```

Get the controllers for VM

#### Arguments

- `vm` *vim.VirtualMachine* - VM instance

#### Returns

- `list` - list of controllers

### VSPHERE().get_dc

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L104)

```python
def get_dc(name):
```

Gets the Datacenter

#### Arguments

- `name` *str* - Datacenter name

#### Returns

- `vim.Datacenter` - Datacenter instance

### VSPHERE().get_pool

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L135)

```python
def get_pool(name, dc, cluster):
```

Gets the Resource pool

#### Arguments

- `name` *str* - Resource pool name
- `dc` *str* - Datacenter name
- `cluster` *str* - Cluster name

#### Returns

- `vim.ResourcePool` - Resource pool instance

### VSPHERE().get_search_index

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L78)

```python
@property
def get_search_index():
```

Get the search index

#### Returns

- `vim.SearchIndex` - Instance of Search Index

### VSPHERE().get_unit_number

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L220)

```python
def get_unit_number(vm):
```

Gets the available unit number for the disk

#### Arguments

- `vm` *vim.VirtualMachine* - VM instance

#### Returns

- `int` - available unit number for disk

### VSPHERE().get_vm_by_ip

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L89)

```python
def get_vm_by_ip(ip, dc, vm_search=True):
```

Gets the VM using IP address

#### Arguments

- `ip` *str* - IP address
- `dc` *str* - Datacenter name
- `vm_search` *bool* - Search for VMs if True, Hosts if False

#### Returns

- `vim.VirtualMachine` - VM instance

### VSPHERE().get_vm_in_pool_by_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/vsphere.py#L169)

```python
def get_vm_in_pool_by_name(name, dc, cluster, pool):
```

Gets the VM instance in a resource pool

#### Arguments

- `name` *str* - VM name
- `dc` *str* - Datacenter name
- `cluster` *str* - Cluster name
- `pool` *str* - pool name

#### Returns

- `vim.VirtualMachine` - VM instances
