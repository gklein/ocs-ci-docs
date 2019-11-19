# AWS

> Auto-generated documentation for [ocs_ci.utility.aws](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / AWS
    - [AWS](#aws)
        - [AWS().append_security_group](#awsappend_security_group)
        - [AWS().attach_volume](#awsattach_volume)
        - [AWS().block_instances_access](#awsblock_instances_access)
        - [AWS().create_security_group](#awscreate_security_group)
        - [AWS().create_volume](#awscreate_volume)
        - [AWS().create_volume_and_attach](#awscreate_volume_and_attach)
        - [AWS().delete_security_group](#awsdelete_security_group)
        - [AWS().delete_volume](#awsdelete_volume)
        - [AWS().detach_and_delete_volume](#awsdetach_and_delete_volume)
        - [AWS().detach_volume](#awsdetach_volume)
        - [AWS().ec2_client](#awsec2_client)
        - [AWS().ec2_resource](#awsec2_resource)
        - [AWS().get_all_security_groups](#awsget_all_security_groups)
        - [AWS().get_availability_zone_id_by_instance_id](#awsget_availability_zone_id_by_instance_id)
        - [AWS().get_ec2_instance](#awsget_ec2_instance)
        - [AWS().get_ec2_instance_volumes](#awsget_ec2_instance_volumes)
        - [AWS().get_instances_by_name_pattern](#awsget_instances_by_name_pattern)
        - [AWS().get_instances_status_by_id](#awsget_instances_status_by_id)
        - [AWS().get_security_groups_by_instance_id](#awsget_security_groups_by_instance_id)
        - [AWS().get_volumes_by_name_pattern](#awsget_volumes_by_name_pattern)
        - [AWS().get_vpc_id_by_instance_id](#awsget_vpc_id_by_instance_id)
        - [AWS().remove_security_group](#awsremove_security_group)
        - [AWS().restart_ec2_instances](#awsrestart_ec2_instances)
        - [AWS().restore_instances_access](#awsrestore_instances_access)
        - [AWS().start_ec2_instances](#awsstart_ec2_instances)
        - [AWS().stop_ec2_instances](#awsstop_ec2_instances)
        - [AWS().store_security_groups_for_instances](#awsstore_security_groups_for_instances)
    - [AWSTimeoutException](#awstimeoutexception)
    - [get_data_volumes](#get_data_volumes)
    - [get_instances_ids_and_names](#get_instances_ids_and_names)
    - [get_vpc_id_by_node_obj](#get_vpc_id_by_node_obj)

## AWS

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L19)

```python
class AWS(object):
    def __init__(region_name=None):
```

This is wrapper class for AWS

### AWS().append_security_group

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L528)

```python
def append_security_group(security_group_id, instance_id):
```

Append security group to selected ec2 nodes

#### Arguments

- `instance_id` *str* - Instances to attach security group
- `security_group_id(str)` - Security group to attach

- `print` *out* - security group <id> added to selected nodes

### AWS().attach_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L232)

```python
def attach_volume(volume, instance_id, device='/dev/sdx'):
```

Attach volume to an ec2 instance

#### Arguments

- `volume` *Volume* - Volume instance
- `instance_id` *str* - id of instance where to attach the volume
- `device` *str* - The name of the device where to attach (default: /dev/sdx)

### AWS().block_instances_access

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L597)

```python
def block_instances_access(security_group_id, instances_id):
```

Block ec2 instances by:

- Append security group without access permissions
- Remove original security groups

#### Arguments

- `security_group_id` *str* - security group without access permissions
- `instances_id` *list* - list of ec2 instances ids

### AWS().create_security_group

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L499)

```python
def create_security_group(group_name, dict_permissions, vpc_id):
```

Create security group with predefined group name and permissions

#### Arguments

- `group_name` *str* - Group name (aws tag: "Group Name")
- `dict_permissions` *dict* - The security group's inbound/outbound permissions
- `vpc_id(str)` - For group to be attached

#### Returns

- `str` - newly created security group id

### AWS().create_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L171)

```python
def create_volume(
    availability_zone,
    name,
    encrypted=False,
    size=100,
    timeout=20,
    volume_type='gp2',
):
```

Create volume

#### Arguments

- `availability_zone` *str* - The availability zone e.g.: us-west-1b
- `name` *str* - The name of the volume
- `encrypted` *boolean* - True if encrypted, False otherwise
    - `(default` - False)
- `size` *int* - The size in GB (default: 100)
- `timeout` *int* - The timeout in seconds for volume creation (default: 20)
- `volume_type` *str* - 'standard'|'io1'|'gp2'|'sc1'|'st1'
    - `(default` - gp2)

#### Returns

- `Volume` - AWS Resource instance of the newly created volume

### AWS().create_volume_and_attach

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L249)

```python
def create_volume_and_attach(
    availability_zone,
    instance_id,
    name,
    device='/dev/sdx',
    encrypted=False,
    size=100,
    timeout=20,
    volume_type='gp2',
):
```

Create volume and attach to instance

#### Arguments

- `availability_zone` *str* - The availability zone e.g.: us-west-1b
- `instance_id` *str* - The id of the instance where to attach the volume
- `name` *str* - The name of volume
- `device` *str* - The name of device where to attach (default: /dev/sdx)
- `encrypted` *boolean* - True if encrypted, False otherwise
    - `(default` - False)
- `size` *int* - The size in GB (default: 100)
- `timeout` *int* - The timeout in seconds for volume creation (default: 20)
- `volume_type` *str* - 'standard'|'io1'|'gp2'|'sc1'|'st1'
    - `(default` - gp2)

### AWS().delete_security_group

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L567)

```python
def delete_security_group(security_group_id):
```

Delete selected security group
print out: Security group <id> deleted

#### Arguments

- `security_group_id` *str* - Id of selected security group

### AWS().delete_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L349)

```python
def delete_volume(volume):
```

Delete an ec2 volume from AWS

#### Arguments

- `volume` *Volume* - The volume to delete

### AWS().detach_and_delete_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L364)

```python
def detach_and_delete_volume(volume, timeout=120):
```

Detach volume if attached and then delete it from AWS

#### Arguments

- `volume` *Volume* - The volume to delete
- `timeout` *int* - Timeout in seconds for API calls

### AWS().detach_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L309)

```python
def detach_volume(volume, timeout=120):
```

Detach volume if attached

#### Arguments

- `volume` *Volume* - The volume to delete
- `timeout` *int* - Timeout in seconds for API calls

#### Returns

- `Volume` - ec2 Volume instance

### AWS().ec2_client

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L37)

```python
@property
def ec2_client():
```

Property for ec2 client

#### Returns

- `boto3.client` - instance of ec2

### AWS().ec2_resource

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L51)

```python
@property
def ec2_resource():
```

Property for ec2 resource

#### Returns

boto3.resource instance of ec2 resource

### AWS().get_all_security_groups

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L466)

```python
def get_all_security_groups():
```

Get all security groups in AWS region

#### Returns

- `list` - All security groups

### AWS().get_availability_zone_id_by_instance_id

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L156)

```python
def get_availability_zone_id_by_instance_id(instance_id):
```

Fetch availability zone out of ec2 node (EC2.Instances.placement)

#### Arguments

- `instance_id` *str* - ID of the instance - to get availability zone info from ec2 node

#### Returns

- `str` - availability_zone: The availability zone name

### AWS().get_ec2_instance

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L65)

```python
def get_ec2_instance(instance_id):
```

Get instance of ec2 Instance

#### Arguments

- `instance_id` *str* - The ID of the instance to get

#### Returns

- `boto3.Instance` - instance of ec2 instance resource

### AWS().get_ec2_instance_volumes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L451)

```python
def get_ec2_instance_volumes(instance_id):
```

Get all volumes attached to an ec2 instance

#### Arguments

- `instance_id` *str* - The ec2 instance ID

#### Returns

- `list` - ec2 Volume instances

### AWS().get_instances_by_name_pattern

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L78)

```python
def get_instances_by_name_pattern(pattern):
```

Get instances by Name tag pattern

The instance details do not contain all the values but just those we
are consuming.

Those parameters we are storing for instance are:
* id: id of instance
* avz: Availability Zone
* name: The value of Tag Name if define otherwise None
* vpc_id: VPC ID
* security_groups: Security groups of the instance

#### Arguments

- `pattern` *str* - Pattern of tag name like:
    pbalogh-testing-cluster-55jx2-worker*

#### Returns

- `list` - contains dictionaries with instance details mentioned above

### AWS().get_instances_status_by_id

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L127)

```python
def get_instances_status_by_id(instance_id):
```

Get instances by ID

#### Arguments

- `instance_id` *str* - ID of the instance

#### Returns

- `str` - The instance status

### AWS().get_security_groups_by_instance_id

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L483)

```python
def get_security_groups_by_instance_id(instance_id):
```

Get all attached security groups of ec2 instance

#### Arguments

- `instance_id` *str* - Required instance to get security groups from it

#### Returns

- `list` - all_sg_ids: all attached security groups id.

### AWS().get_volumes_by_name_pattern

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L281)

```python
def get_volumes_by_name_pattern(pattern):
```

Get volumes by pattern

#### Arguments

- `pattern` *str* - Pattern of volume name (e.g. '*cl-vol-*')

#### Returns

- `list` - Volume information like id and attachments

### AWS().get_vpc_id_by_instance_id

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L141)

```python
def get_vpc_id_by_instance_id(instance_id):
```

Fetch vpc id out of ec2 node (EC2.Instances.vpc_id)

#### Arguments

- `instance_id` *str* - ID of the instance - to get vpc id info from ec2 node

#### Returns

- `str` - vpc_id: The vpc id

### AWS().remove_security_group

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L548)

```python
def remove_security_group(security_group_id, instance_id):
```

Remove security group from selected ec2 instance (by instance id)
print out: security group <id> removed from selected nodes

#### Arguments

- `security_group_id` *str* - Security group to be removed
- `instance_id` *str* - Instance attached with selected security group

### AWS().restart_ec2_instances

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L436)

```python
def restart_ec2_instances(instances, wait=False, force=True):
```

Stop and start ec2 instances

#### Arguments

- `instances` *dict* - A dictionary of instance IDs and names to restart
- `wait` *bool* - True in case wait for status is needed,
    False otherwise
- `force` *bool* - True for force instance stop, False otherwise

### AWS().restore_instances_access

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L616)

```python
def restore_instances_access(
    security_group_id_to_remove,
    original_security_group_dict,
):
```

Restore access to instances by removing blocking security group and append original security group

#### Arguments

security_group_id_to_remove (str):
- `original_security_group_dict` *dict* - keys: blocked instances: ec2 instances id
    - `values` - list of original security groups

### AWS().start_ec2_instances

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L407)

```python
def start_ec2_instances(instances, wait=False):
```

Starting an instance

#### Arguments

- `instances` *dict* - A dictionary of instance IDs and names to start
- `wait` *bool* - True in case wait for status is needed,
    False otherwise

### AWS().stop_ec2_instances

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L376)

```python
def stop_ec2_instances(instances, wait=False, force=True):
```

Stopping an instance

#### Arguments

- `instances` *dict* - A dictionary of instance IDs and names to stop
- `wait` *bool* - True in case wait for status is needed,
    False otherwise
- `force` *bool* - True for force instance stop, False otherwise

### AWS().store_security_groups_for_instances

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L579)

```python
def store_security_groups_for_instances(instances_id):
```

Stored all security groups attached to selected ec2 instances

#### Arguments

- `instances_id` *list* - ec2 instance_id

#### Returns

- `dict` - security_group_dict: keys: blocked instances: ec2_instances ids
    - `values` - list of original security groups of each instance

## AWSTimeoutException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L15)

```python
class AWSTimeoutException(Exception):
```

## get_data_volumes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L650)

```python
def get_data_volumes(deviceset_pvs):
```

Get the instance data volumes (which doesn't include root FS)

#### Arguments

- `deviceset_pvs` *list* - PVC objects of the deviceset PVs

#### Returns

- `list` - ec2 Volume instances

## get_instances_ids_and_names

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L633)

```python
def get_instances_ids_and_names(instances):
```

Get the instances IDs and names according to nodes dictionary

#### Arguments

- `instances` *list* - Nodes dictionaries, returned by 'oc get node -o yaml'

#### Returns

- `dict` - The ID keys and the name values of the instances

## get_vpc_id_by_node_obj

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/aws.py#L670)

```python
def get_vpc_id_by_node_obj(aws_obj, instances):
```

This function getting vpc id by randomly selecting instances out of user aws deployment

#### Arguments

- `aws_obj` *obj* - AWS() object
- `instances` *dict* - cluster ec2 instances objects

#### Returns

- `str` - vpc_id: The vpc id
