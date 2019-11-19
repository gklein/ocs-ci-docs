# Utils

> Auto-generated documentation for [ocs_ci.utility.utils](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / Utils
    - [TimeoutSampler](#timeoutsampler)
        - [TimeoutSampler().wait_for_func_status](#timeoutsamplerwait_for_func_status)
    - [activate_multiple_mdss](#activate_multiple_mdss)
    - [add_path_to_env_path](#add_path_to_env_path)
    - [allow_dir_fragmentation](#allow_dir_fragmentation)
    - [auth_list](#auth_list)
    - [censor_values](#censor_values)
    - [ceph_health_check](#ceph_health_check)
    - [check_if_executable_in_path](#check_if_executable_in_path)
    - [clone_repo](#clone_repo)
    - [create_directory_path](#create_directory_path)
    - [create_rhelpod](#create_rhelpod)
    - [custom_ceph_config](#custom_ceph_config)
    - [decompose_html_attributes](#decompose_html_attributes)
    - [delete_file](#delete_file)
    - [download_file](#download_file)
    - [dump_config_to_file](#dump_config_to_file)
    - [email_reports](#email_reports)
    - [ensure_nightly_build_availability](#ensure_nightly_build_availability)
    - [expose_nightly_ocp_version](#expose_nightly_ocp_version)
    - [file_locking](#file_locking)
    - [fuse_client_io](#fuse_client_io)
    - [fuse_client_md5](#fuse_client_md5)
    - [fuse_mount](#fuse_mount)
    - [get_ceph_version](#get_ceph_version)
    - [get_client_info](#get_client_info)
    - [get_cluster_image](#get_cluster_image)
    - [get_cluster_version](#get_cluster_version)
    - [get_cluster_version_info](#get_cluster_version_info)
    - [get_csi_versions](#get_csi_versions)
    - [get_latest_ds_olm_tag](#get_latest_ds_olm_tag)
    - [get_next_version_available_for_upgrade](#get_next_version_available_for_upgrade)
    - [get_ocs_build_number](#get_ocs_build_number)
    - [get_openshift_client](#get_openshift_client)
    - [get_openshift_installer](#get_openshift_installer)
    - [get_openshift_mirror_url](#get_openshift_mirror_url)
    - [get_random_str](#get_random_str)
    - [get_rook_repo](#get_rook_repo)
    - [get_rook_version](#get_rook_version)
    - [get_testrun_name](#get_testrun_name)
    - [get_url_content](#get_url_content)
    - [is_cluster_running](#is_cluster_running)
    - [kernel_client_io](#kernel_client_io)
    - [kernel_client_md5](#kernel_client_md5)
    - [kernel_mount](#kernel_mount)
    - [mask_secrets](#mask_secrets)
    - [mds_fail_over](#mds_fail_over)
    - [mkdir_pinning](#mkdir_pinning)
    - [ocsci_log_path](#ocsci_log_path)
    - [parse_html_for_email](#parse_html_for_email)
    - [parse_pgsql_logs](#parse_pgsql_logs)
    - [pinned_dir_io](#pinned_dir_io)
    - [prepare_bin_dir](#prepare_bin_dir)
    - [read_file_as_str](#read_file_as_str)
    - [replace_content_in_file](#replace_content_in_file)
    - [run_async](#run_async)
    - [run_cmd](#run_cmd)
    - [run_mcg_cmd](#run_mcg_cmd)
    - [upload_file](#upload_file)
    - [wait_for_co](#wait_for_co)

#### Attributes

- `mounting_dir` - variables: `'/mnt/cephfs/'`

## TimeoutSampler

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L682)

```python
class TimeoutSampler(object):
    def __init__(timeout, sleep, func, *func_args, **func_kwargs):
```

Samples the function output.

This is a generator object that at first yields the output of function
`func`. After the yield, it either raises instance of `timeout_exc_cls` or
sleeps `sleep` seconds.

Yielding the output allows you to handle every value as you wish.

Feel free to set the instance variables.

### TimeoutSampler().wait_for_func_status

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L732)

```python
def wait_for_func_status(result):
```

Get function and run it for given time until success or timeout.
(using __iter__ function)

#### Arguments

- `result` *bool* - Expected result from func.

#### Examples

sample = TimeoutSampler(
    timeout=60, sleep=1, func=some_func, func_arg1="1",
    func_arg2="2"
)
if not sample.wait_for_func_status(result=True):
    raise Exception

## activate_multiple_mdss

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L230)

```python
def activate_multiple_mdss(mds_nodes):
```

## add_path_to_env_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L657)

```python
def add_path_to_env_path(path):
```

Add path to the PATH environment variable (if not already there).

#### Arguments

- `path` *str* - Path which should be added to the PATH env. variable

## allow_dir_fragmentation

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L260)

```python
def allow_dir_fragmentation(mds_nodes):
```

## auth_list

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L77)

```python
def auth_list(clients, mon_node):
```

## censor_values

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1398)

```python
def censor_values(data_to_censor):
```

This function censor values in dictionary keys that match pattern defined
in config_keys_patterns_to_censor in constants.

#### Arguments

- `data_to_censor` *dict* - Data to censor.

## ceph_health_check

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1141)

```python
@retry((CephHealthException, CommandFailed), tries=20, delay=30, backoff=1)
def ceph_health_check(namespace=None):
```

Exec `ceph health` cmd on tools pod to determine health of cluster.

#### Arguments

- `namespace` *str* - Namespace of OCS
    - `(default` - config.ENV_DATA['cluster_namespace'])

#### Raises

- `CephHealthException` - If the ceph health returned is not HEALTH_OK
- `CommandFailed` - If the command to retrieve the tools pod name or the
    command to get ceph health returns a non-zero exit code

#### Returns

- `boolean` - True if HEALTH_OK

## check_if_executable_in_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1303)

```python
def check_if_executable_in_path(exec_name):
```

Checks whether an executable can be found in the $PATH

#### Arguments

- `exec_name` - Name of executable to look for

#### Returns

- `Boolean` - Whether the executable was found

## clone_repo

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1207)

```python
def clone_repo(url, location, branch='master', to_checkout=None):
```

Clone a repository or checkout latest changes if it already exists at
    specified location.

#### Arguments

- `url` *str* - location of the repository to clone
- `location` *str* - path where the repository will be cloned to
- `branch` *str* - branch name to checkout
- `to_checkout` *str* - commit id or tag to checkout

## create_directory_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1078)

```python
def create_directory_path(path):
```

Creates directory if path doesn't exists

## create_rhelpod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1428)

```python
def create_rhelpod(namespace, pod_name):
```

Creates the RHEL pod

#### Arguments

- `namespace` *str* - Namespace to create RHEL pod
- `pod_name` *str* - Pod name

#### Returns

- `pod` - Pod instance for RHEL

## custom_ceph_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L307)

```python
def custom_ceph_config(suite_config, custom_config, custom_config_file):
```

Combines and returns custom configuration overrides for ceph.
Hierarchy is as follows:
    custom_config > custom_config_file > suite_config

#### Arguments

- `suite_config` - ceph_conf_overrides that currently exist in the test suite
- `custom_config` - custom config args provided by the cli (these all go to the global scope)
- `custom_config_file` - path to custom config yaml file provided by the cli

Returns
    New value to be used for ceph_conf_overrides in test config

## decompose_html_attributes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L818)

```python
def decompose_html_attributes(soup, attributes):
```

Decomposes the given html attributes

#### Arguments

- `soup` *obj* - BeautifulSoup object
- `attributes` *list* - attributes to decompose

- `Returns` - None

## delete_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L672)

```python
def delete_file(file_name):
```

Delete file_name

#### Arguments

- `file_name` *str* - Path to the file you want to delete

## download_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L432)

```python
def download_file(url, filename):
```

Download a file from a specified url

#### Arguments

- `url` *str* - URL of the file to download
- `filename` *str* - Name of the file to write the download to

## dump_config_to_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1413)

```python
def dump_config_to_file(file_path):
```

Dump the config to the yaml file with censored secret values.

#### Arguments

- `file_path` *str* - Path to file where to write the configuration.

## email_reports

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L872)

```python
def email_reports():
```

Email results of test run

## ensure_nightly_build_availability

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L591)

```python
def ensure_nightly_build_availability(build_url):
```

## expose_nightly_ocp_version

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L469)

```python
def expose_nightly_ocp_version(version):
```

This helper function exposes latest nightly version of OCP. When the
version string ends with .nightly (e.g. 4.2.0-0.nightly) it will expose
the version to latest accepted OCP build
(e.g. 4.2.0-0.nightly-2019-08-08-103722)

#### Arguments

- `version` *str* - Verison of OCP

#### Returns

- `str` - Version of OCP exposed to full version if latest nighly passed

## file_locking

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L189)

```python
def file_locking(client):
```

## fuse_client_io

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L141)

```python
def fuse_client_io(client, mounting_dir):
```

## fuse_client_md5

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L167)

```python
def fuse_client_md5(fuse_clients, md5sum_list1):
```

## fuse_mount

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L100)

```python
def fuse_mount(fuse_clients, mounting_dir):
```

## get_ceph_version

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L969)

```python
def get_ceph_version():
```

Gets the ceph version

#### Returns

- `str` - ceph version

## get_client_info

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L53)

```python
def get_client_info(ceph_nodes, clients):
```

## get_cluster_image

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L958)

```python
def get_cluster_image():
```

Gets the cluster image

#### Returns

- `str` - cluster image

## get_cluster_version

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L947)

```python
def get_cluster_version():
```

Gets the cluster version

#### Returns

- `str` - cluster version

## get_cluster_version_info

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L908)

```python
def get_cluster_version_info():
```

Gets the complete cluster version information

#### Returns

- `dict` - cluster version information

## get_csi_versions

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L999)

```python
def get_csi_versions():
```

Gets the CSI related version information

#### Returns

- `dict` - CSI related version information

## get_latest_ds_olm_tag

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1233)

```python
def get_latest_ds_olm_tag(upgrade=False):
```

This function returns latest tag of OCS downstream registry or one before
latest if upgrade parameter is True

#### Arguments

- `upgrade` *str* - If True then it returns one version of the build before
    the latest.

#### Returns

- `str` - latest tag for downstream image from quay registry

#### Raises

- `TagNotFoundException` - In case no tag found

## get_next_version_available_for_upgrade

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1270)

```python
def get_next_version_available_for_upgrade(current_tag):
```

This function returns the tag built after the current_version

#### Arguments

- `current_tag` *str* - Current build tag from which to search the next one
    build tag.

#### Returns

- `str` - tag for downstream image from quay registry built after
    the current_tag.

#### Raises

- `TagNotFoundException` - In case no tag suitable for upgrade found

## get_ocs_build_number

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L923)

```python
def get_ocs_build_number():
```

Gets the build number for ocs operator

#### Returns

- `str` - build number for ocs operator version

## get_openshift_client

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L543)

```python
def get_openshift_client(version=None, bin_dir=None, force_download=False):
```

Download the OpenShift client binary, if not already present.
Update env. PATH and get path of the oc binary.

#### Arguments

- `version` *str* - Version of the client to download
    - `(default` - config.RUN['client_version'])
- `bin_dir` *str* - Path to bin directory (default: config.RUN['bin_dir'])
- `force_download` *bool* - Force client download even if already present

#### Returns

- `str` - Path to the client binary

## get_openshift_installer

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L495)

```python
def get_openshift_installer(version=None, bin_dir=None, force_download=False):
```

Download the OpenShift installer binary, if not already present.
Update env. PATH and get path of the openshift installer binary.

#### Arguments

- `version` *str* - Version of the installer to download
- `bin_dir` *str* - Path to bin directory (default: config.RUN['bin_dir'])
- `force_download` *bool* - Force installer download even if already present

#### Returns

- `str` - Path to the installer binary

## get_openshift_mirror_url

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L600)

```python
def get_openshift_mirror_url(file_name, version):
```

Format url to OpenShift mirror (for client and installer download).

#### Arguments

- `file_name` *str* - Name of file
- `version` *str* - Version of the installer or client to download

#### Returns

- `str` - Url of the desired file (installer or client)

#### Raises

- `UnsupportedOSType` - In case the OS type is not supported
- `UnavailableBuildException` - In case the build url is not reachable

## get_random_str

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L760)

```python
def get_random_str(size=13):
```

generates the random string of given size

#### Arguments

- `size` *int* - number of random characters to generate

#### Returns

str : string of random characters of given size

## get_rook_repo

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1179)

```python
def get_rook_repo(branch='master', to_checkout=None):
```

Clone and checkout the rook repository to specific branch/commit.

#### Arguments

- `branch` *str* - Branch name to checkout
- `to_checkout` *str* - Commit id or tag to checkout

## get_rook_version

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L984)

```python
def get_rook_version():
```

Gets the rook version

#### Returns

- `str` - rook version

## get_testrun_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1105)

```python
def get_testrun_name():
```

Prepare testrun ID for Polarion (and other reports).

Return config.REPORTING["polarion"]["testrun_name"], if configured.
Otherwise prepare testrun ID based on Upstream/Downstream information,
OCS version and used markers.

#### Returns

- `str` - String containing testrun ID

## get_url_content

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L450)

```python
def get_url_content(url):
```

Return URL content

#### Arguments

- `url` *str* - URL address to return

#### Returns

- `str` - Content of URL

#### Raises

- `AssertionError` - When couldn't load URL

## is_cluster_running

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L811)

```python
def is_cluster_running(cluster_path):
```

## kernel_client_io

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L154)

```python
def kernel_client_io(client, mounting_dir):
```

## kernel_client_md5

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L178)

```python
def kernel_client_md5(kernel_clients, md5sum_list2):
```

## kernel_mount

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L119)

```python
def kernel_mount(mounting_dir, mon_node_ip, kernel_clients):
```

## mask_secrets

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L358)

```python
def mask_secrets(plaintext, secrets):
```

Replace secrets in plaintext with asterisks

#### Arguments

- `plaintext` *str* - The plaintext to remove the secrets from
- `secrets` *list* - List of secret strings to replace in the plaintext

#### Returns

- `str` - The censored version of plaintext

## mds_fail_over

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L270)

```python
def mds_fail_over(mds_nodes):
```

## mkdir_pinning

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L242)

```python
def mkdir_pinning(clients, range1, range2, dir_name, pin_val):
```

## ocsci_log_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1089)

```python
def ocsci_log_path():
```

Construct the full path for the log directory.

#### Returns

- `str` - full path for ocs-ci log directory

## parse_html_for_email

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L835)

```python
def parse_html_for_email(soup):
```

Parses the html and filters out the unnecessary data/tags/attributes
for email reporting

#### Arguments

- `soup` *obj* - BeautifulSoup object

## parse_pgsql_logs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1030)

```python
def parse_pgsql_logs(data):
```

Parse the pgsql benchmark data from ripsaw and return
the data in list format

#### Arguments

- `data` *str* - log data from pgsql bench run

#### Returns

- `list_data` *list* - data digestable by scripts with below
                format
    - `eg` - ( with only one item in the list)
    - `[{'num_clients'` - '2', 'num_threads': '7', 'latency_avg': '7',
     - `'lat_stddev'` - '0', 'tps_incl': '234', 'tps_excl': '243'}]

## pinned_dir_io

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L282)

```python
def pinned_dir_io(clients, mds_fail_over, num_of_files, range1, range2):
```

## prepare_bin_dir

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L642)

```python
def prepare_bin_dir(bin_dir=None):
```

Prepare bin directory for OpenShift client and installer

#### Arguments

- `bin_dir` *str* - Path to bin directory (default: config.RUN['bin_dir'])

## read_file_as_str

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1342)

```python
def read_file_as_str(filepath):
```

Reads the file content

#### Arguments

- `filepath` *str* - File to read

#### Returns

str : File contents in string

## replace_content_in_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1358)

```python
def replace_content_in_file(file, old, new):
```

Replaces contents in file, if old value is not found, it adds
new value to the file

#### Arguments

- `file` *str* - Name of the file in which contents will be replaced
- `old` *str* - Data to search for
- `new` *str* - Data to replace the old value

## run_async

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L775)

```python
def run_async(command):
```

Run command locally and return without waiting for completion

#### Arguments

- `command` *str* - The command to run.

#### Returns

An open descriptor to be used by the calling function.

#### Examples

command = 'oc delete pvc pvc1'
proc = run_async(command)
ret, out, err = proc.async_communicate()

## run_cmd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L376)

```python
def run_cmd(cmd, secrets=None, **kwargs):
```

Run an arbitrary command locally

#### Arguments

- `cmd` *str* - command to run

- `secrets` *list* - A list of secrets to be masked with asterisks
    This kwarg is popped in order to not interfere with
    subprocess.run(**kwargs)

#### Raises

- `CommandFailed` - In case the command execution fails

#### Returns

(str) Decoded stdout of command

## run_mcg_cmd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L416)

```python
def run_mcg_cmd(cmd, namespace=None):
```

Invokes [run_cmd](#run_cmd) with a noobaa prefix

#### Arguments

- `cmd` - The MCG command to be run
- `namespace` - The namespace to use for the command

#### Returns

- `str` - Stdout of the command

## upload_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1317)

```python
def upload_file(server, localpath, remotepath, user=None, password=None):
```

Upload a file to remote server

#### Arguments

- `server` *str* - Name of the server to upload
- `localpath` *str* - Local file to upload
- `remotepath` *str* - Target path on the remote server. filename should be included
- `user` *str* - User to use for the remote connection

## wait_for_co

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/utils.py#L1384)

```python
@retry(CommandFailed, tries=100, delay=10, backoff=1)
def wait_for_co(operator):
```

Waits for ClusterOperator to created

#### Arguments

- `operator` *str* - Name of the ClusterOperator
