# Pod

> Auto-generated documentation for [ocs_ci.ocs.resources.pod](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py) module.

Pod related functionalities and context info

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Ocs](../index.md#ocs) / [Resources](index.md#resources) / Pod
    - [Pod](#pod)
        - [Pod().add_role](#podadd_role)
        - [Pod().copy_to_server](#podcopy_to_server)
        - [Pod().exec_bash_cmd_on_pod](#podexec_bash_cmd_on_pod)
        - [Pod().exec_ceph_cmd](#podexec_ceph_cmd)
        - [Pod().exec_cmd_on_node](#podexec_cmd_on_node)
        - [Pod().exec_cmd_on_pod](#podexec_cmd_on_pod)
        - [Pod().get_fio_results](#podget_fio_results)
        - [Pod().get_labels](#podget_labels)
        - [Pod().get_storage_path](#podget_storage_path)
        - [Pod().install_packages](#podinstall_packages)
        - [Pod().labels](#podlabels)
        - [Pod().name](#podname)
        - [Pod().namespace](#podnamespace)
        - [Pod().roles](#podroles)
        - [Pod().run_git_clone](#podrun_git_clone)
        - [Pod().run_io](#podrun_io)
        - [Pod().workload_setup](#podworkload_setup)
    - [cal_md5sum](#cal_md5sum)
    - [check_file_existence](#check_file_existence)
    - [delete_pods](#delete_pods)
    - [get_admin_key_from_ceph_tools](#get_admin_key_from_ceph_tools)
    - [get_all_pods](#get_all_pods)
    - [get_ceph_tools_pod](#get_ceph_tools_pod)
    - [get_cephfs_provisioner_pod](#get_cephfs_provisioner_pod)
    - [get_cephfsplugin_provisioner_pods](#get_cephfsplugin_provisioner_pods)
    - [get_file_path](#get_file_path)
    - [get_fio_rw_iops](#get_fio_rw_iops)
    - [get_mds_pods](#get_mds_pods)
    - [get_mgr_pods](#get_mgr_pods)
    - [get_mon_pods](#get_mon_pods)
    - [get_operator_pods](#get_operator_pods)
    - [get_osd_pods](#get_osd_pods)
    - [get_plugin_pods](#get_plugin_pods)
    - [get_pod_count](#get_pod_count)
    - [get_pod_logs](#get_pod_logs)
    - [get_pod_node](#get_pod_node)
    - [get_pod_obj](#get_pod_obj)
    - [get_pods_having_label](#get_pods_having_label)
    - [get_pvc_name](#get_pvc_name)
    - [get_rbd_provisioner_pod](#get_rbd_provisioner_pod)
    - [get_rbdfsplugin_provisioner_pods](#get_rbdfsplugin_provisioner_pods)
    - [get_used_space_on_mount_point](#get_used_space_on_mount_point)
    - [list_ceph_images](#list_ceph_images)
    - [plugin_provisioner_leader](#plugin_provisioner_leader)
    - [run_io_and_verify_mount_point](#run_io_and_verify_mount_point)
    - [run_io_in_bg](#run_io_in_bg)
    - [upload](#upload)
    - [validate_pods_are_respinned_and_running_state](#validate_pods_are_respinned_and_running_state)
    - [verify_data_integrity](#verify_data_integrity)
    - [verify_node_name](#verify_node_name)

Each pod in the openshift cluster will have a corresponding pod object

## Pod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L44)

```python
class Pod(OCS):
    def __init__(**kwargs):
```

Handles per pod related context

#### See also

- [OCS](ocs.md#ocs)

### Pod().add_role

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L94)

```python
def add_role(role):
```

Adds a new role for this pod

#### Arguments

- `role` *str* - New role to be assigned for this pod

### Pod().copy_to_server

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L317)

```python
def copy_to_server(server, authkey, localpath, remotepath, user=None):
```

Upload a file from pod to server

#### Arguments

- `server` *str* - Name of the server to upload
- `authkey` *str* - Authentication file (.pem file)
- `localpath` *str* - Local file/dir in pod to upload
- `remotepath` *str* - Target path on the remote server
- `user` *str* - User name to connect to server

### Pod().exec_bash_cmd_on_pod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L150)

```python
def exec_bash_cmd_on_pod(command):
```

Execute a pure bash command on a pod via oc exec where you can use
bash syntaxt like &&, ||, ;, for loop and so on.

#### Arguments

- `command` *str* - The command to execute on the given pod

#### Returns

- `str` - stdout of the command

### Pod().exec_ceph_cmd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L176)

```python
def exec_ceph_cmd(ceph_cmd, format='json-pretty'):
```

Execute a Ceph command on the Ceph tools pod

#### Arguments

- `ceph_cmd` *str* - The Ceph command to execute on the Ceph tools pod
- `format` *str* - The returning output format of the Ceph command

#### Returns

- `dict` - Ceph command output

#### Raises

- `CommandFailed` - In case the pod is not a toolbox pod

### Pod().exec_cmd_on_node

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L338)

```python
def exec_cmd_on_node(server, authkey, cmd, user=None):
```

Run command on a remote server from pod

#### Arguments

- `server` *str* - Name of the server to run the command
- `authkey` *str* - Authentication file (.pem file)
- `cmd` *str* - command to run on server from pod
- `user` *str* - User name to connect to server

### Pod().exec_cmd_on_pod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L130)

```python
def exec_cmd_on_pod(command, out_yaml_format=True, secrets=None, **kwargs):
```

Execute a command on a pod (e.g. oc rsh)

#### Arguments

- `command` *str* - The command to execute on the given pod
- `out_yaml_format` *bool* - whether to return yaml loaded python
    object OR to return raw output

- `secrets` *list* - A list of secrets to be masked with asterisks
    This kwarg is popped in order to not interfere with
    subprocess.run(**kwargs)

#### Returns

- `Munch` *Obj* - This object represents a returned yaml file

### Pod().get_fio_results

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L103)

```python
def get_fio_results():
```

Get FIO execution results

#### Returns

- `dict` - Dictionary represents the FIO execution results

#### Raises

- `Exception` - In case of exception from FIO

### Pod().get_labels

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L164)

```python
def get_labels():
```

Get labels from pod

#### Raises

- `NotFoundError` - If resource not found

#### Returns

- `dict` - All the openshift labels on a given pod

### Pod().get_storage_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L204)

```python
def get_storage_path(storage_type='fs'):
```

Get the pod volume mount path or device path

#### Returns

- `str` - The mount path of the volume on the pod (e.g. /var/lib/www/html/) if storage_type is fs
     else device path of raw block pv

### Pod().install_packages

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L303)

```python
def install_packages(packages):
```

Install packages in a Pod

#### Arguments

- `packages` *list* - List of packages to install

### Pod().labels

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L87)

```python
@property
def labels():
```

### Pod().name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L75)

```python
@property
def name():
```

### Pod().namespace

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L79)

```python
@property
def namespace():
```

### Pod().roles

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L83)

```python
@property
def roles():
```

### Pod().run_git_clone

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L290)

```python
def run_git_clone():
```

Execute git clone on a pod to simulate a Jenkins user

### Pod().run_io

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L243)

```python
def run_io(
    storage_type,
    size,
    io_direction='rw',
    rw_ratio=75,
    jobs=1,
    runtime=60,
    depth=4,
    fio_filename=None,
):
```

Execute FIO on a pod
This operation will run in background and will store the results in
'self.thread.result()'.
In order to wait for the output and not continue with the test until
FIO is done, call self.thread.result() right after calling run_io.
See tests/manage/test_pvc_deletion_during_io.py::test_run_io
for usage of FIO

#### Arguments

- `storage_type` *str* - 'fs' or 'block'
- `size` *str* - Size in MB, e.g. '200M'
- `io_direction` *str* - Determines the operation:
    'ro', 'wo', 'rw' (default: 'rw')
- `rw_ratio` *int* - Determines the reads and writes using a
    <rw_ratio>%/100-<rw_ratio>%
    (e.g. the default is 75 which means it is 75%/25% which
    equivalent to 3 reads are performed for every 1 write)
- `jobs` *int* - Number of jobs to execute FIO
- `runtime` *int* - Number of seconds IO should run for
- `depth` *int* - IO depth
- `fio_filename(str)` - Name of fio file created on app pod's mount point

### Pod().workload_setup

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L224)

```python
def workload_setup(storage_type, jobs=1):
```

Do setup on pod for running FIO

#### Arguments

- `storage_type` *str* - 'fs' or 'block'
- `jobs` *int* - Number of jobs to execute FIO

## cal_md5sum

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L496)

```python
def cal_md5sum(pod_obj, file_name):
```

Calculates the md5sum of the file

#### Arguments

- `pod_obj` *Pod* - The object of the pod
- `file_name` *str* - The name of the file for which md5sum to be calculated

#### Returns

- `str` - The md5sum of the file

## check_file_existence

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L459)

```python
def check_file_existence(pod_obj, file_path):
```

Check if file exists inside the pod

#### Arguments

- `pod_obj` *Pod* - The object of the pod
- `file_path` *str* - The full path of the file to look for inside
    the pod

#### Returns

- `bool` - True if the file exist, False otherwise

## delete_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L841)

```python
def delete_pods(pod_objs):
```

Deletes list of the pod objects

#### Arguments

- `pod_objs` *list* - List of the pod objects to be deleted

#### Returns

- `bool` - True if deletion is successful

## get_admin_key_from_ceph_tools

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L611)

```python
def get_admin_key_from_ceph_tools():
```

Fetches admin key secret from ceph

#### Returns

admin keyring encoded with base64 as a string

## get_all_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L358)

```python
def get_all_pods(namespace=None, selector=None):
```

Get all pods in a namespace.

#### Arguments

- `namespace` *str* - Name of the namespace
    If namespace is None - get all pods
selector (list) : List of the resource selector to search with
    - `Example` - ['alertmanager','prometheus']

#### Returns

- `list` - List of Pod objects

## get_ceph_tools_pod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L381)

```python
def get_ceph_tools_pod():
```

Get the Ceph tools pod

#### Returns

- `Pod` *object* - The Ceph tools pod object

## get_cephfs_provisioner_pod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L430)

```python
def get_cephfs_provisioner_pod():
```

Get the cephfs provisioner pod

#### Returns

- `Pod` *object* - The cephfs provisioner pod object

## get_cephfsplugin_provisioner_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L745)

```python
def get_cephfsplugin_provisioner_pods(
    cephfsplugin_provisioner_label=constants.CSI_CEPHFSPLUGIN_PROVISIONER_LABEL,
    namespace=None,
):
```

Fetches info about CSI Cephfs plugin provisioner pods in the cluster

#### Arguments

- `cephfsplugin_provisioner_label` *str* - label associated with cephfs
    provisioner pods
    - `(default` - defaults.CSI_CEPHFSPLUGIN_PROVISIONER_LABEL)
- `namespace` *str* - Namespace in which ceph cluster lives
    - `(default` - defaults.ROOK_CLUSTER_NAMESPACE)

#### Returns

list : csi-cephfsplugin-provisioner Pod objects

## get_file_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L477)

```python
def get_file_path(pod_obj, file_name):
```

Get the full path of the file

#### Arguments

- `pod_obj` *Pod* - The object of the pod
- `file_name` *str* - The name of the file for which path to get

#### Returns

- `str` - The full path of the file

## get_fio_rw_iops

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L545)

```python
def get_fio_rw_iops(pod_obj):
```

Execute FIO on a pod

#### Arguments

- `pod_obj` *Pod* - The object of the pod

## get_mds_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L663)

```python
def get_mds_pods(mds_label=constants.MDS_APP_LABEL, namespace=None):
```

Fetches info about mds pods in the cluster

#### Arguments

- `mds_label` *str* - label associated with mds pods
    - `(default` - defaults.MDS_APP_LABEL)
- `namespace` *str* - Namespace in which ceph cluster lives
    - `(default` - defaults.ROOK_CLUSTER_NAMESPACE)

#### Returns

list : of mds pod objects

## get_mgr_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L701)

```python
def get_mgr_pods(mgr_label=constants.MGR_APP_LABEL, namespace=None):
```

Fetches info about mgr pods in the cluster

#### Arguments

- `mgr_label` *str* - label associated with mgr pods
    - `(default` - defaults.MGR_APP_LABEL)
- `namespace` *str* - Namespace in which ceph cluster lives
    - `(default` - defaults.ROOK_CLUSTER_NAMESPACE)

#### Returns

list : of mgr pod objects

## get_mon_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L682)

```python
def get_mon_pods(mon_label=constants.MON_APP_LABEL, namespace=None):
```

Fetches info about mon pods in the cluster

#### Arguments

- `mon_label` *str* - label associated with mon pods
    - `(default` - defaults.MON_APP_LABEL)
- `namespace` *str* - Namespace in which ceph cluster lives
    - `(default` - defaults.ROOK_CLUSTER_NAMESPACE)

#### Returns

list : of mon pod objects

## get_operator_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L1025)

```python
def get_operator_pods(
    operator_label=constants.OPERATOR_LABEL,
    namespace=None,
):
```

Fetches info about rook-ceph-operator pods in the cluster

#### Arguments

- `operator_label` *str* - Label associated with rook-ceph-operator pod
- `namespace` *str* - Namespace in which ceph cluster lives

#### Returns

list : of rook-ceph-operator pod objects

## get_osd_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L720)

```python
def get_osd_pods(osd_label=constants.OSD_APP_LABEL, namespace=None):
```

Fetches info about osd pods in the cluster

#### Arguments

- `osd_label` *str* - label associated with osd pods
    - `(default` - defaults.OSD_APP_LABEL)
- `namespace` *str* - Namespace in which ceph cluster lives
    - `(default` - defaults.ROOK_CLUSTER_NAMESPACE)

#### Returns

list : of osd pod objects

## get_plugin_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L950)

```python
def get_plugin_pods(interface, namespace=None):
```

Fetches info of csi-cephfsplugin pods or csi-rbdplugin pods

#### Arguments

- `interface` *str* - Interface type. eg: CephBlockPool, CephFileSystem
- `namespace` *str* - Name of cluster namespace

#### Returns

list : csi-cephfsplugin pod objects or csi-rbdplugin pod objects

## get_pod_count

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L739)

```python
def get_pod_count(label, namespace=None):
```

## get_pod_logs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L807)

```python
def get_pod_logs(pod_name, container=None):
```

Get logs from a given pod

pod_name (str): Name of the pod
container (str): Name of the container

#### Returns

- `str` - Output from 'oc get logs <pod_name> command

## get_pod_node

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L826)

```python
def get_pod_node(pod_obj):
```

Get the node that the pod is running on

#### Arguments

- `pod_obj` *OCS* - The pod object

#### Returns

- `OCP` - The node object

## get_pod_obj

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L791)

```python
def get_pod_obj(name, namespace=None):
```

Returns the pod obj for the given pod

#### Arguments

- `name` *str* - Name of the resources

#### Returns

obj : A pod object

## get_pods_having_label

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L647)

```python
def get_pods_having_label(label, namespace):
```

Fetches pod resources with given label in given namespace

#### Arguments

- `label` *str* - label which pods might have
- `namespace` *str* - Namespace in which to be looked up

#### Returns

- `dict` - of pod info

## get_pvc_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L917)

```python
def get_pvc_name(pod_obj):
```

Function to get pvc_name from pod_obj

#### Arguments

- `pod_obj` *str* - The pod object

#### Returns

- `pvc_name` *str* - The pvc_name on a given pod_obj

## get_rbd_provisioner_pod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L412)

```python
def get_rbd_provisioner_pod():
```

Get the RBD provisioner pod

#### Returns

- `Pod` *object* - The RBD provisioner pod object

## get_rbdfsplugin_provisioner_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L768)

```python
def get_rbdfsplugin_provisioner_pods(
    rbdplugin_provisioner_label=constants.CSI_RBDPLUGIN_PROVISIONER_LABEL,
    namespace=None,
):
```

Fetches info about CSI Cephfs plugin provisioner pods in the cluster

#### Arguments

- `rbdplugin_provisioner_label` *str* - label associated with RBD
    provisioner pods
    - `(default` - defaults.CSI_RBDPLUGIN_PROVISIONER_LABEL)
- `namespace` *str* - Namespace in which ceph cluster lives
    - `(default` - defaults.ROOK_CLUSTER_NAMESPACE)

#### Returns

list : csi-rbdplugin-provisioner Pod objects

## get_used_space_on_mount_point

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L932)

```python
def get_used_space_on_mount_point(pod_obj):
```

Get the used space on a mount point

#### Arguments

- `pod_obj` *POD* - The pod object

#### Returns

- `int` - Percentage represent the used space on the mount point

## list_ceph_images

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L448)

```python
def list_ceph_images(pool_name='rbd'):
```

#### Arguments

- `pool_name` *str* - Name of the pool to get the ceph images

- `Returns` *List* - List of RBD images in the pool

## plugin_provisioner_leader

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L971)

```python
def plugin_provisioner_leader(interface, namespace=None):
```

Find csi-cephfsplugin-provisioner or csi-rbdplugin-provisioner leader pod

#### Arguments

- `interface` *str* - Interface type. eg: CephBlockPool, CephFileSystem
- `namespace` *str* - Name of cluster namespace

#### Returns

- `Pod` - csi-cephfsplugin-provisioner or csi-rbdplugin-provisioner leader
    pod

## run_io_and_verify_mount_point

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L623)

```python
def run_io_and_verify_mount_point(pod_obj, bs='10M', count='950'):
```

Run I/O on mount point

#### Arguments

- `pod_obj` *Pod* - The object of the pod
- `bs` *str* - Read and write up to bytes at a time
- `count` *str* - Copy only N input blocks

#### Returns

- `used_percentage` *str* - Used percentage on mount point

## run_io_in_bg

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L563)

```python
def run_io_in_bg(pod_obj, expect_to_fail=False):
```

Run I/O in the background

#### Arguments

- `pod_obj` *Pod* - The object of the pod
- `expect_to_fail` *bool* - True for the command to be expected to fail
    (disruptive operations), False otherwise

#### Returns

- `Thread` - A thread of the I/O execution

## upload

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L1042)

```python
def upload(pod_name, localpath, remotepath):
```

Upload a file to pod

#### Arguments

- `pod_name` *str* - Name of the pod
- `localpath` *str* - Local file to upload
- `remotepath` *str* - Target path on the pod

## validate_pods_are_respinned_and_running_state

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L856)

```python
def validate_pods_are_respinned_and_running_state(pod_objs_list):
```

Verifies the list of the pods are respinned and in running state

#### Arguments

- `pod_objs_list` *list* - List of the pods obj

#### Returns

bool : True if the pods are respinned and running, False otherwise

## verify_data_integrity

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L516)

```python
def verify_data_integrity(pod_obj, file_name, original_md5sum):
```

Verifies existence and md5sum of file created from first pod

#### Arguments

- `pod_obj` *Pod* - The object of the pod
- `file_name` *str* - The name of the file for which md5sum to be calculated
- `original_md5sum` *str* - The original md5sum of the file

#### Returns

- `bool` - True if the file exists and md5sum matches

#### Raises

- `AssertionError` - If file doesn't exist or md5sum mismatch

## verify_node_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/pod.py#L886)

```python
def verify_node_name(pod_obj, node_name):
```

Verifies that the pod is running on a particular node

#### Arguments

- `pod_obj` *Pod* - The pod object
- `node_name` *str* - The name of node to check

#### Returns

- `bool` - True if the pod is running on a particular node, False otherwise
