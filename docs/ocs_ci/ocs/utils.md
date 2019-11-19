# Utils

> Auto-generated documentation for [ocs_ci.ocs.utils](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Utils
    - [apply_oc_resource](#apply_oc_resource)
    - [check_ceph_healthly](#check_ceph_healthly)
    - [cleanup_ceph_nodes](#cleanup_ceph_nodes)
    - [collect_ocs_logs](#collect_ocs_logs)
    - [config_ntp](#config_ntp)
    - [create_ceph_conf](#create_ceph_conf)
    - [create_ceph_nodes](#create_ceph_nodes)
    - [create_nodes](#create_nodes)
    - [create_oc_resource](#create_oc_resource)
    - [generate_repo_file](#generate_repo_file)
    - [get_ceph_versions](#get_ceph_versions)
    - [get_iso_file_url](#get_iso_file_url)
    - [get_openstack_driver](#get_openstack_driver)
    - [get_pod_name_by_pattern](#get_pod_name_by_pattern)
    - [get_public_network](#get_public_network)
    - [get_root_permissions](#get_root_permissions)
    - [hard_reboot](#hard_reboot)
    - [keep_alive](#keep_alive)
    - [node_power_failure](#node_power_failure)
    - [open_firewall_port](#open_firewall_port)
    - [run_must_gather](#run_must_gather)
    - [search_ethernet_interface](#search_ethernet_interface)
    - [set_cdn_repo](#set_cdn_repo)
    - [setup_cdn_repos](#setup_cdn_repos)
    - [setup_ceph_toolbox](#setup_ceph_toolbox)
    - [setup_deb_cdn_repo](#setup_deb_cdn_repo)
    - [setup_deb_repos](#setup_deb_repos)
    - [setup_repos](#setup_repos)
    - [setup_vm_node](#setup_vm_node)
    - [store_cluster_state](#store_cluster_state)
    - [update_ca_cert](#update_ca_cert)
    - [write_docker_daemon_json](#write_docker_daemon_json)

## apply_oc_resource

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L658)

```python
def apply_oc_resource(
    template_name,
    cluster_path,
    _templating,
    template_data=None,
    template_dir='ocs-deployment',
):
```

Apply an oc resource after rendering the specified template with
the rook data from cluster_conf.

#### Arguments

- `template_name` *str* - Name of the ocs-deployment config template
- `cluster_path` *str* - Path to cluster directory, where files will be
    written
- `_templating` *Templating* - Object of Templating class used for
    templating
- `template_data` *dict* - Data for render template (default: {})
- `template_dir` *str* - Directory under templates dir where template
    - `exists` *(default* - ocs-deployment)

## check_ceph_healthly

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L193)

```python
def check_ceph_healthly(
    ceph_mon,
    num_osds,
    num_mons,
    mon_container=None,
    timeout=300,
):
```

Function to check ceph is in healthy state

#### Arguments

- `ceph_mon` - monitor node
- `num_osds` - number of osds in cluster
- `num_mons` - number of mons in cluster
- `mon_container` - monitor container name if monitor is placed in the container
- `timeout` - 300 seconds(default) max time to check
  if cluster is not healthy within timeout period
         return 1

#### Returns

return 0 when ceph is in healthy state, else 1

## cleanup_ceph_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L116)

```python
def cleanup_ceph_nodes(osp_cred, pattern=None, timeout=300):
```

## collect_ocs_logs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L725)

```python
def collect_ocs_logs(dir_name, ocp=True, ocs=True):
```

Collects OCS logs

#### Arguments

- `dir_name` *str* - directory name to store OCS logs. Logs will be stored
    in dir_name suffix with _ocs_logs.
- `ocp` *bool* - Whether to gather OCP logs
- `ocs` *bool* - Whether to gather OCS logs

## config_ntp

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L400)

```python
def config_ntp(ceph_node):
```

## create_ceph_conf

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L264)

```python
def create_ceph_conf(
    fsid,
    mon_hosts,
    pg_num='128',
    pgp_num='128',
    size='2',
    auth='cephx',
    pnetwork='172.16.0.0/12',
    jsize='1024',
):
```

## create_ceph_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L33)

```python
def create_ceph_nodes(
    cluster_conf,
    inventory,
    osp_cred,
    run_id,
    instances_name=None,
):
```

## create_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L524)

```python
@retry(LibcloudError, tries=5, delay=15)
def create_nodes(conf, inventory, osp_cred, run_id, instances_name=None):
```

## create_oc_resource

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L570)

```python
def create_oc_resource(
    template_name,
    cluster_path,
    _templating,
    template_data=None,
    template_dir='ocs-deployment',
):
```

Create an oc resource after rendering the specified template with
the rook data from cluster_conf.

#### Arguments

- `template_name` *str* - Name of the ocs-deployment config template
- `cluster_path` *str* - Path to cluster directory, where files will be
    written
- `_templating` *Templating* - Object of Templating class used for
    templating
- `template_data` *dict* - Data for render template (default: {})
- `template_dir` *str* - Directory under templates dir where template
    - `exists` *(default* - ocs-deployment)

## generate_repo_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L256)

```python
def generate_repo_file(base_url, repos):
```

## get_ceph_versions

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L412)

```python
def get_ceph_versions(ceph_nodes, containerized=False):
```

Log and return the ceph or ceph-ansible versions for each node in the cluster.

#### Arguments

- `ceph_nodes` - nodes in the cluster
- `containerized` - is the cluster containerized or not

#### Returns

A dict of the name / version pair for each node or container in the cluster

## get_iso_file_url

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L260)

```python
def get_iso_file_url(base_url):
```

## get_openstack_driver

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L94)

```python
def get_openstack_driver(yaml):
```

## get_pod_name_by_pattern

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L603)

```python
def get_pod_name_by_pattern(pattern='client', namespace=None, filter=None):
```

In a given namespace find names of the pods that match
the given pattern

#### Arguments

- `pattern` *str* - name of the pod with given pattern
- `namespace` *str* - Namespace value
- `filter` *str* - pod name to filter from the list

#### Returns

- `pod_list` *list* - List of pod names matching the pattern

## get_public_network

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L514)

```python
def get_public_network():
```

Get the configured public network subnet for nodes in the cluster.

#### Returns

(str) public network subnet

## get_root_permissions

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L504)

```python
def get_root_permissions(node, path):
```

Transfer ownership of root to current user for the path given. Recursive.

#### Arguments

node(ceph.ceph.CephNode):
- `path` - file path

## hard_reboot

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L467)

```python
def hard_reboot(gyaml, name=None):
```

## keep_alive

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L167)

```python
def keep_alive(ceph_nodes):
```

## node_power_failure

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L480)

```python
def node_power_failure(gyaml, sleep_time=300, name=None):
```

## open_firewall_port

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L389)

```python
def open_firewall_port(ceph_node, port, protocol):
```

Opens firewall ports for given node

#### Arguments

- `ceph_node` *ceph.ceph.CephNode* - ceph node
- `port` *str* - port
- `protocol` *str* - protocol

## run_must_gather

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L691)

```python
def run_must_gather(log_dir_path, image, command=None):
```

Runs the must-gather tool against the cluster

#### Arguments

- `log_dir_path` *str* - directory for dumped must-gather logs
- `image` *str* - must-gather image registry path
- `command` *str* - optional command to execute within the must-gather image

## search_ethernet_interface

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L378)

```python
def search_ethernet_interface(ceph_node, ceph_node_list):
```

Search interface on the given node node which allows every node in the cluster accesible by it's shortname.

#### Arguments

- `ceph_node` *ceph.ceph.CephNode* - node where check is performed
- `ceph_node_list(list)` - node list to check

## set_cdn_repo

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L350)

```python
def set_cdn_repo(node, repos):
```

## setup_cdn_repos

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L319)

```python
def setup_cdn_repos(ceph_nodes, build=None):
```

## setup_ceph_toolbox

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L636)

```python
def setup_ceph_toolbox():
```

Setup ceph-toolbox - also checks if toolbox exists, if it exists it
behaves as noop.

## setup_deb_cdn_repo

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L308)

```python
def setup_deb_cdn_repo(node, build=None):
```

## setup_deb_repos

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L287)

```python
def setup_deb_repos(node, ubuntu_repo):
```

## setup_repos

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L172)

```python
def setup_repos(ceph, base_url, installer_url=None):
```

## setup_vm_node

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L90)

```python
def setup_vm_node(node, ceph_nodes, **params):
```

## store_cluster_state

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L563)

```python
def store_cluster_state(ceph_cluster_object, ceph_clusters_file_name):
```

## update_ca_cert

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L357)

```python
def update_ca_cert(node, cert_url, timeout=120):
```

## write_docker_daemon_json

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/utils.py#L368)

```python
def write_docker_daemon_json(json_text, node):
```

Write given string to /etc/docker/daemon/daemon

#### Arguments

- `json_text` - json string
- `node` *ceph.ceph.CephNode* - Ceph node object
