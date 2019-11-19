# Platform Nodes

> Auto-generated documentation for [ocs_ci.ocs.platform_nodes](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Platform Nodes
    - [AWSNodes](#awsnodes)
        - [AWSNodes().attach_volume](#awsnodesattach_volume)
        - [AWSNodes().detach_volume](#awsnodesdetach_volume)
        - [AWSNodes().get_data_volumes](#awsnodesget_data_volumes)
        - [AWSNodes().get_ec2_instances](#awsnodesget_ec2_instances)
        - [AWSNodes().get_node_by_attached_volume](#awsnodesget_node_by_attached_volume)
        - [AWSNodes().restart_nodes](#awsnodesrestart_nodes)
        - [AWSNodes().restart_nodes_teardown](#awsnodesrestart_nodes_teardown)
        - [AWSNodes().start_nodes](#awsnodesstart_nodes)
        - [AWSNodes().stop_nodes](#awsnodesstop_nodes)
        - [AWSNodes().wait_for_volume_attach](#awsnodeswait_for_volume_attach)
    - [NodesBase](#nodesbase)
        - [NodesBase().attach_volume](#nodesbaseattach_volume)
        - [NodesBase().detach_volume](#nodesbasedetach_volume)
        - [NodesBase().get_data_volumes](#nodesbaseget_data_volumes)
        - [NodesBase().get_node_by_attached_volume](#nodesbaseget_node_by_attached_volume)
        - [NodesBase().restart_nodes](#nodesbaserestart_nodes)
        - [NodesBase().restart_nodes_teardown](#nodesbaserestart_nodes_teardown)
        - [NodesBase().start_nodes](#nodesbasestart_nodes)
        - [NodesBase().stop_nodes](#nodesbasestop_nodes)
        - [NodesBase().wait_for_volume_attach](#nodesbasewait_for_volume_attach)
    - [PlatformNodesFactory](#platformnodesfactory)
        - [PlatformNodesFactory().get_nodes_platform](#platformnodesfactoryget_nodes_platform)
    - [VMWareNodes](#vmwarenodes)
        - [VMWareNodes().attach_volume](#vmwarenodesattach_volume)
        - [VMWareNodes().detach_volume](#vmwarenodesdetach_volume)
        - [VMWareNodes().get_data_volumes](#vmwarenodesget_data_volumes)
        - [VMWareNodes().get_node_by_attached_volume](#vmwarenodesget_node_by_attached_volume)
        - [VMWareNodes().restart_nodes](#vmwarenodesrestart_nodes)
        - [VMWareNodes().restart_nodes_teardown](#vmwarenodesrestart_nodes_teardown)
        - [VMWareNodes().start_nodes](#vmwarenodesstart_nodes)
        - [VMWareNodes().stop_nodes](#vmwarenodesstop_nodes)
        - [VMWareNodes().wait_for_volume_attach](#vmwarenodeswait_for_volume_attach)

## AWSNodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L132)

```python
class AWSNodes(NodesBase):
    def __init__():
```

AWS EC2 instances class

#### See also

- [NodesBase](#nodesbase)

### AWSNodes().attach_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L252)

```python
def attach_volume(node, volume):
```

Attach a data volume to an instance

#### Arguments

- `node` *OCS* - The EC2 instance to attach the volume to
- `volume` *Volume* - The volume to delete

### AWSNodes().detach_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L242)

```python
def detach_volume(volume):
```

Detach a volume from an EC2 instance

#### Arguments

- `volume` *Volume* - The volume to delete

### AWSNodes().get_data_volumes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L153)

```python
def get_data_volumes():
```

Get the data EBS volumes

#### Returns

- `list` - EBS Volume instances

### AWSNodes().get_ec2_instances

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L140)

```python
def get_ec2_instances(nodes):
```

Get the EC2 instances dicts

#### Arguments

- `nodes` *list* - The OCS objects of the nodes

#### Returns

- `dict` - The EC2 instances dicts (IDs and names)

### AWSNodes().get_node_by_attached_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L164)

```python
def get_node_by_attached_volume(volume):
```

Get node OCS object of the EC2 instance that has the volume attached to

#### Arguments

- `volume` *Volume* - The volume to get the EC2 according to

#### Returns

- `OCS` - The OCS object of the EC2 instance

### AWSNodes().restart_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L223)

```python
def restart_nodes(nodes, wait=True, force=True):
```

Restart EC2 instances

#### Arguments

- `nodes` *list* - The OCS objects of the nodes
- `wait` *bool* - True in case wait for status is needed,
    False otherwise
- `force` *bool* - True for force instance stop, False otherwise

### AWSNodes().restart_nodes_teardown

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L308)

```python
def restart_nodes_teardown():
```

Make sure all EC2 instances are up. To be used in the test teardown

### AWSNodes().start_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L208)

```python
def start_nodes(nodes, wait=True):
```

Start EC2 instances

#### Arguments

- `nodes` *list* - The OCS objects of the nodes
- `wait` *bool* - True for waiting the instances to start, False otherwise

### AWSNodes().stop_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L192)

```python
def stop_nodes(nodes, wait=True):
```

Stop EC2 instances

#### Arguments

- `nodes` *list* - The OCS objects of the nodes
- `wait` *bool* - True for waiting the instances to stop, False otherwise

### AWSNodes().wait_for_volume_attach

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L275)

```python
def wait_for_volume_attach(volume):
```

Wait for an EBS volume to be attached to an EC2 instance.
This is used as when detaching the EBS volume from the EC2 instance,
re-attach should take place automatically

#### Arguments

- `volume` *Volume* - The volume to wait for to be attached

#### Returns

- `bool` - True if the volume has been attached to the
    instance, False otherwise

## NodesBase

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L28)

```python
class NodesBase(object):
```

A base class for nodes related operations.
Should be inherited by specific platform classes

### NodesBase().attach_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L64)

```python
def attach_volume(node, volume):
```

### NodesBase().detach_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L59)

```python
def detach_volume(node):
```

### NodesBase().get_data_volumes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L34)

```python
def get_data_volumes():
```

### NodesBase().get_node_by_attached_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L39)

```python
def get_node_by_attached_volume(volume):
```

### NodesBase().restart_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L54)

```python
def restart_nodes(nodes):
```

### NodesBase().restart_nodes_teardown

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L74)

```python
def restart_nodes_teardown():
```

### NodesBase().start_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L49)

```python
def start_nodes(nodes, wait=True):
```

### NodesBase().stop_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L44)

```python
def stop_nodes(nodes, wait=True):
```

### NodesBase().wait_for_volume_attach

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L69)

```python
def wait_for_volume_attach(volume):
```

## PlatformNodesFactory

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L15)

```python
class PlatformNodesFactory():
    def __init__():
```

A factory class to get specific nodes platform object

### PlatformNodesFactory().get_nodes_platform

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L23)

```python
def get_nodes_platform():
```

## VMWareNodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L80)

```python
class VMWareNodes(NodesBase):
```

VMWare nodes class

#### See also

- [NodesBase](#nodesbase)

### VMWareNodes().attach_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L116)

```python
def attach_volume(node, volume):
```

### VMWareNodes().detach_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L111)

```python
def detach_volume(node):
```

### VMWareNodes().get_data_volumes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L85)

```python
def get_data_volumes():
```

### VMWareNodes().get_node_by_attached_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L90)

```python
def get_node_by_attached_volume(volume):
```

### VMWareNodes().restart_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L106)

```python
def restart_nodes(nodes):
```

### VMWareNodes().restart_nodes_teardown

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L126)

```python
def restart_nodes_teardown():
```

### VMWareNodes().start_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L101)

```python
def start_nodes(nodes, wait=True):
```

### VMWareNodes().stop_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L96)

```python
def stop_nodes(nodes, wait=True):
```

### VMWareNodes().wait_for_volume_attach

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/platform_nodes.py#L121)

```python
def wait_for_volume_attach(volume):
```
