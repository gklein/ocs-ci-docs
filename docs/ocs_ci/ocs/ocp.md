# OCP

> Auto-generated documentation for [ocs_ci.ocs.ocp](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py) module.

General OCP object

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / OCP
    - [OCP](#ocp)
        - [OCP().add_label](#ocpadd_label)
        - [OCP().api_version](#ocpapi_version)
        - [OCP().apply](#ocpapply)
        - [OCP().check_function_supported](#ocpcheck_function_supported)
        - [OCP().check_name_is_specified](#ocpcheck_name_is_specified)
        - [OCP().check_phase](#ocpcheck_phase)
        - [OCP().create](#ocpcreate)
        - [OCP().data](#ocpdata)
        - [OCP().delete](#ocpdelete)
        - [OCP().describe](#ocpdescribe)
        - [OCP().exec_oc_cmd](#ocpexec_oc_cmd)
        - [OCP().exec_oc_debug_cmd](#ocpexec_oc_debug_cmd)
        - [OCP().get](#ocpget)
        - [OCP().get_resource_status](#ocpget_resource_status)
        - [OCP().get_user_token](#ocpget_user_token)
        - [OCP().kind](#ocpkind)
        - [OCP().login](#ocplogin)
        - [OCP().namespace](#ocpnamespace)
        - [OCP().new_project](#ocpnew_project)
        - [OCP().patch](#ocppatch)
        - [OCP().reload_data](#ocpreload_data)
        - [OCP().resource_name](#ocpresource_name)
        - [OCP().wait_for_delete](#ocpwait_for_delete)
        - [OCP().wait_for_phase](#ocpwait_for_phase)
        - [OCP().wait_for_resource](#ocpwait_for_resource)
    - [rsync](#rsync)
    - [switch_to_default_rook_cluster_project](#switch_to_default_rook_cluster_project)
    - [switch_to_project](#switch_to_project)

## OCP

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L30)

```python
class OCP(object):
    def __init__(
        api_version='v1',
        kind='Service',
        namespace=None,
        resource_name='',
    ):
```

A basic OCP object to run basic 'oc' commands

### OCP().add_label

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L309)

```python
def add_label(resource_name, label):
```

Adds a new label for this pod

#### Arguments

- `resource_name` *str* - Name of the resource you want to label
- `label` *str* - New label to be assigned for this pod
    - `E.g` - "label=app='rook-ceph-mds'"

### OCP().api_version

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L58)

```python
@property
def api_version():
```

### OCP().apply

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L274)

```python
def apply(yaml_file):
```

Applies configuration changes to a resource

#### Arguments

- `yaml_file` *str* - Path to a yaml file to use in 'oc apply -f
    file.yaml

#### Returns

- `dict` - Dictionary represents a returned yaml file

### OCP().check_function_supported

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L541)

```python
def check_function_supported(support_var):
```

Check if the resource supports the functionality based on the
support_var.

#### Arguments

- `support_var` *bool* - True if functionality is supported, False
    otherwise.

#### Raises

- `NotSupportedFunctionError` - If support_var == False

### OCP().check_name_is_specified

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L523)

```python
def check_name_is_specified(resource_name=''):
```

Check if the name of the resource is specified in class level and
if not raise the exception.

#### Raises

- `ResourceNameNotSpecifiedException` - in case the name is not
    specified.

### OCP().check_phase

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L559)

```python
def check_phase(phase):
```

Check phase of resource

#### Arguments

- `phase` *str* - Phase of resource object

#### Returns

- `bool` - True if phase of object is the same as passed one, False
    otherwise.

#### Raises

- `NotSupportedFunctionError` - If resource doesn't have phase!
- `ResourceNameNotSpecifiedException` - in case the name is not
    specified.

### OCP().create

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L206)

```python
def create(yaml_file=None, resource_name='', out_yaml_format=True):
```

Creates a new resource

#### Arguments

- `yaml_file` *str* - Path to a yaml file to use in 'oc create -f
    file.yaml
- `resource_name` *str* - Name of the resource you want to create
- `out_yaml_format` *bool* - Determines if the output should be
    formatted to a yaml like string

#### Returns

- `dict` - Dictionary represents a returned yaml file

### OCP().data

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L74)

```python
@property
def data():
```

### OCP().delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L237)

```python
def delete(yaml_file=None, resource_name='', wait=True, force=False):
```

Deletes a resource

#### Arguments

- `yaml_file` *str* - Path to a yaml file to use in 'oc delete -f
    file.yaml
- `resource_name` *str* - Name of the resource you want to delete
- `wait` *bool* - Determines if the delete command should wait to
    completion
- `force` *bool* - True for force deletion with --grace-period=0,
    False otherwise

#### Returns

- `dict` - Dictionary represents a returned yaml file

#### Raises

- `CommandFailed` - In case yaml_file and resource_name wasn't provided

### OCP().describe

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L184)

```python
def describe(resource_name='', selector=None, all_namespaces=False):
```

Get command - 'oc describe <resource>'

#### Arguments

- `resource_name` *str* - The resource name to fetch
- `selector` *str* - The label selector to look for
- `all_namespaces` *bool* - Equal to oc describe <resource> -A

#### Examples

describe('my-pv1')

#### Returns

- `dict` - Dictionary represents a returned yaml file

### OCP().exec_oc_cmd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L87)

```python
def exec_oc_cmd(command, out_yaml_format=True, secrets=None, **kwargs):
```

Executing 'oc' command

#### Arguments

- `command` *str* - The command to execute (e.g. create -f file.yaml)
    without the initial 'oc' at the beginning

- `out_yaml_format` *bool* - whether to return  yaml loaded python
    object or raw output

- `secrets` *list* - A list of secrets to be masked with asterisks
    This kwarg is popped in order to not interfere with
    subprocess.run(**kwargs)

#### Returns

- `dict` - Dictionary represents a returned yaml file

### OCP().exec_oc_debug_cmd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L126)

```python
def exec_oc_debug_cmd(node, cmd_list):
```

Function to execute "oc debug" command on OCP node

#### Arguments

- `node` *str* - Node name where the command to be executed
- `cmd_list` *list* - List of commands eg: ['cmd1', 'cmd2']

#### Returns

- `out` *str* - Returns output of the executed command/commands

#### Raises

- `CommandFailed` - When failure in command execution

### OCP().get

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L153)

```python
def get(
    resource_name='',
    out_yaml_format=True,
    selector=None,
    all_namespaces=False,
):
```

Get command - 'oc get <resource>'

#### Arguments

- `resource_name` *str* - The resource name to fetch
- `out_yaml_format` *bool* - Adding '-o yaml' to oc command
- `selector` *str* - The label selector to look for
- `all_namespaces` *bool* - Equal to oc get <resource> -A

#### Examples

get('my-pv1')

#### Returns

- `dict` - Dictionary represents a returned yaml file

### OCP().get_resource_status

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L493)

```python
def get_resource_status(resource_name):
```

Get the resource status based on:
'oc get <resource_kind> <resource_name>' command

#### Arguments

- `resource_name` *str* - The name of the resource to get its status

#### Returns

- `str` - The status returned by 'oc get' command not in the 'yaml'
    format

### OCP().get_user_token

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L352)

```python
def get_user_token():
```

Get user access token

#### Returns

- `str` - access token

### OCP().kind

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L62)

```python
@property
def kind():
```

### OCP().login

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L337)

```python
def login(user, password):
```

Logs user in

#### Arguments

- `user` *str* - Name of user to be logged in
- `password` *str* - Password of user to be logged in

#### Returns

- `str` - output of login command

### OCP().namespace

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L66)

```python
@property
def namespace():
```

### OCP().new_project

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L322)

```python
def new_project(project_name):
```

Creates a new project

#### Arguments

- `project_name` *str* - Name of the project to be created

#### Returns

- `bool` - True in case project creation succeeded, False otherwise

### OCP().patch

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L288)

```python
def patch(resource_name, params, type='json'):
```

Applies changes to resources

#### Arguments

- `resource_name` *str* - Name of the resource
- `params` *str* - Changes to be added to the resource
- `type` *str* - Type of the operation

#### Returns

- `bool` - True in case if changes are applied. False otherwise

### OCP().reload_data

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L81)

```python
def reload_data():
```

Reloading data of OCP object

### OCP().resource_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L70)

```python
@property
def resource_name():
```

### OCP().wait_for_delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L453)

```python
def wait_for_delete(resource_name='', timeout=60, sleep=3):
```

Wait for a resource to be deleted

#### Arguments

- `resource_name` *str* - The name of the resource to wait
    for (e.g.my-pv1)
- `timeout` *int* - Time in seconds to wait
- `sleep` *int* - Sampling time in seconds

#### Raises

- `CommandFailed` - If failed to verify the resource deletion
- `TimeoutError` - If resource is not deleted within specified timeout

#### Returns

- `bool` - True in case resource deletion is successful

### OCP().wait_for_phase

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L596)

```python
@retry(ResourceInUnexpectedState, tries=4, delay=5, backoff=1)
def wait_for_phase(phase, timeout=300, sleep=5):
```

Wait till phase of resource is the same as required one passed in
the phase parameter.

#### Arguments

- `phase` *str* - Desired phase of resource object
- `timeout` *int* - Timeout in seconds to wait for desired phase
- `sleep` *int* - Time in seconds to sleep between attempts

#### Raises

- `ResourceInUnexpectedState` - In case the resource is not in expected
    phase.
- `NotSupportedFunctionError` - If resource doesn't have phase!
- `ResourceNameNotSpecifiedException` - in case the name is not
    specified.

### OCP().wait_for_resource

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L363)

```python
def wait_for_resource(
    condition,
    resource_name='',
    selector=None,
    resource_count=0,
    timeout=60,
    sleep=3,
):
```

Wait for a resource to reach to a desired condition

#### Arguments

- `condition` *str* - The desired state the resource that is sampled
    from 'oc get <kind> <resource_name>' command
- `resource_name` *str* - The name of the resource to wait
    for (e.g.my-pv1)
- `selector` *str* - The resource selector to search with.
    - `Example` - 'app=rook-ceph-mds'
- `resource_count` *int* - How many resources expected to be
- `timeout` *int* - Time in seconds to wait
- `sleep` *int* - Sampling time in seconds

#### Returns

- `bool` - True in case all resources reached desired condition,
    False otherwise

## rsync

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L659)

```python
def rsync(src, dst, node, dst_node=True, extra_params=''):
```

This function will rsync source folder to destination path.
You can rsync local folder to the node or vice versa depends on
dst_node parameter. By default the rsync is from local to the node.

#### Arguments

- `src` *str* - Source path of folder to rsync.
- `dst` *str* - Destination path where to rsync.
- `node` *str* - Node to/from copy.
- `dst_node` *bool* - True if the destination (dst) is the node, False
    when dst is the local folder.
- `extra_params` *str* - "See: oc rsync --help for the extra params"

## switch_to_default_rook_cluster_project

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L649)

```python
def switch_to_default_rook_cluster_project():
```

Switch to default project

#### Returns

- `bool` - True on success, False otherwise

## switch_to_project

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ocp.py#L627)

```python
def switch_to_project(project_name):
```

Switch to another project

#### Arguments

- `project_name` *str* - Name of the project to be switched to

#### Returns

- `bool` - True on success, False otherwise
