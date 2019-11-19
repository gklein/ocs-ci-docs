# Ceph

> Auto-generated documentation for [ocs_ci.ocs.ceph](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Ceph
    - [Ceph](#ceph)
        - [Ceph().ansible_config](#cephansible_config)
        - [Ceph().ansible_config](#cephansible_config)
        - [Ceph().ceph_demon_stat](#cephceph_demon_stat)
        - [Ceph().ceph_stable_release](#cephceph_stable_release)
        - [Ceph().check_health](#cephcheck_health)
        - [Ceph().create_rbd_pool](#cephcreate_rbd_pool)
        - [Ceph().distribute_all_yml](#cephdistribute_all_yml)
        - [Ceph().generate_ansible_inventory](#cephgenerate_ansible_inventory)
        - [Ceph.generate_repository_file](#cephgenerate_repository_file)
        - [Ceph().get_ansible_config](#cephget_ansible_config)
        - [Ceph().get_ceph_demons](#cephget_ceph_demons)
        - [Ceph().get_ceph_object](#cephget_ceph_object)
        - [Ceph().get_ceph_objects](#cephget_ceph_objects)
        - [Ceph.get_iso_file_url](#cephget_iso_file_url)
        - [Ceph().get_metadata_list](#cephget_metadata_list)
        - [Ceph().get_node_by_hostname](#cephget_node_by_hostname)
        - [Ceph().get_nodes](#cephget_nodes)
        - [Ceph().get_osd_by_id](#cephget_osd_by_id)
        - [Ceph().get_osd_container_name_by_id](#cephget_osd_container_name_by_id)
        - [Ceph().get_osd_data_partition](#cephget_osd_data_partition)
        - [Ceph().get_osd_data_partition_path](#cephget_osd_data_partition_path)
        - [Ceph().get_osd_device](#cephget_osd_device)
        - [Ceph().get_osd_devices](#cephget_osd_devices)
        - [Ceph().get_osd_metadata](#cephget_osd_metadata)
        - [Ceph().get_osd_service_name](#cephget_osd_service_name)
        - [Ceph().refresh_ansible_config_from_all_yml](#cephrefresh_ansible_config_from_all_yml)
        - [Ceph().rhcs_version](#cephrhcs_version)
        - [Ceph().rhcs_version](#cephrhcs_version)
        - [Ceph().set_ansible_config](#cephset_ansible_config)
        - [Ceph().setup_ceph_firewall](#cephsetup_ceph_firewall)
        - [Ceph().setup_insecure_registry](#cephsetup_insecure_registry)
        - [Ceph().setup_osd_devices](#cephsetup_osd_devices)
        - [Ceph().setup_packages](#cephsetup_packages)
        - [Ceph().setup_ssh_keys](#cephsetup_ssh_keys)
    - [CephClient](#cephclient)
    - [CephDemon](#cephdemon)
        - [CephDemon().ceph_demon_by_container_name](#cephdemonceph_demon_by_container_name)
        - [CephDemon().container_name](#cephdemoncontainer_name)
        - [CephDemon().container_name](#cephdemoncontainer_name)
        - [CephDemon().container_prefix](#cephdemoncontainer_prefix)
        - [CephDemon().exec_command](#cephdemonexec_command)
    - [CephInstaller](#cephinstaller)
        - [CephInstaller().add_iscsi_settings](#cephinstalleradd_iscsi_settings)
        - [CephInstaller().append_to_all_yml](#cephinstallerappend_to_all_yml)
        - [CephInstaller().get_all_yml](#cephinstallerget_all_yml)
        - [CephInstaller().get_installed_ceph_versions](#cephinstallerget_installed_ceph_versions)
        - [CephInstaller().install_ceph_ansible](#cephinstallerinstall_ceph_ansible)
        - [CephInstaller().setup_ansible_site_yml](#cephinstallersetup_ansible_site_yml)
        - [CephInstaller().write_inventory_file](#cephinstallerwrite_inventory_file)
    - [CephNode](#cephnode)
        - [CephNode().chk_lvm_exists](#cephnodechk_lvm_exists)
        - [CephNode().connect](#cephnodeconnect)
        - [CephNode().create_ceph_object](#cephnodecreate_ceph_object)
        - [CephNode().create_lvm](#cephnodecreate_lvm)
        - [CephNode().exec_command](#cephnodeexec_command)
        - [CephNode().generate_id_rsa](#cephnodegenerate_id_rsa)
        - [CephNode().get_allocated_volumes](#cephnodeget_allocated_volumes)
        - [CephNode().get_ceph_demons](#cephnodeget_ceph_demons)
        - [CephNode().get_ceph_objects](#cephnodeget_ceph_objects)
        - [CephNode().get_free_volumes](#cephnodeget_free_volumes)
        - [CephNode().install_lvm_util](#cephnodeinstall_lvm_util)
        - [CephNode().multiple_lvm_scenarios](#cephnodemultiple_lvm_scenarios)
        - [CephNode().obtain_root_permissions](#cephnodeobtain_root_permissions)
        - [CephNode().open_firewall_port](#cephnodeopen_firewall_port)
        - [CephNode().reconnect](#cephnodereconnect)
        - [CephNode().remove_ceph_object](#cephnoderemove_ceph_object)
        - [CephNode().role](#cephnoderole)
        - [CephNode().search_ethernet_interface](#cephnodesearch_ethernet_interface)
        - [CephNode().set_eth_interface](#cephnodeset_eth_interface)
        - [CephNode().set_internal_ip](#cephnodeset_internal_ip)
        - [CephNode().setup_deb_cdn_repos](#cephnodesetup_deb_cdn_repos)
        - [CephNode().setup_deb_repos](#cephnodesetup_deb_repos)
        - [CephNode().setup_rhel_cdn_repos](#cephnodesetup_rhel_cdn_repos)
        - [CephNode().setup_rhel_repos](#cephnodesetup_rhel_repos)
        - [CephNode().write_docker_daemon_json](#cephnodewrite_docker_daemon_json)
        - [CephNode().write_file](#cephnodewrite_file)
    - [CephObject](#cephobject)
        - [CephObject().exec_command](#cephobjectexec_command)
        - [CephObject().pkg_type](#cephobjectpkg_type)
        - [CephObject().write_file](#cephobjectwrite_file)
    - [CephObjectFactory](#cephobjectfactory)
        - [CephObjectFactory().create_ceph_object](#cephobjectfactorycreate_ceph_object)
    - [CephOsd](#cephosd)
        - [CephOsd().container_name](#cephosdcontainer_name)
        - [CephOsd().is_active](#cephosdis_active)
        - [CephOsd().is_active](#cephosdis_active)
    - [NodeVolume](#nodevolume)
    - [RolesContainer](#rolescontainer)
        - [RolesContainer().append](#rolescontainerappend)
        - [RolesContainer().clear](#rolescontainerclear)
        - [RolesContainer().equals](#rolescontainerequals)
        - [RolesContainer().extend](#rolescontainerextend)
        - [RolesContainer().remove](#rolescontainerremove)
        - [RolesContainer().update_role](#rolescontainerupdate_role)
    - [SSHConnectionManager](#sshconnectionmanager)
        - [SSHConnectionManager().client](#sshconnectionmanagerclient)
        - [SSHConnectionManager().get_client](#sshconnectionmanagerget_client)
        - [SSHConnectionManager().get_transport](#sshconnectionmanagerget_transport)
        - [SSHConnectionManager().transport](#sshconnectionmanagertransport)

## Ceph

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L23)

```python
class Ceph(object):
    def __init__(name, node_list=None):
```

### Ceph().ansible_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L407)

```python
@property
def ansible_config():
```

### Ceph().ansible_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L411)

```python
@ansible_config.setter
def ansible_config(ansible_config):
```

### Ceph().ceph_demon_stat

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L426)

```python
@property
def ceph_demon_stat():
```

Retrieves expected numbers for demons of each role

#### Returns

- `dict` - Ceph demon stats

### Ceph().ceph_stable_release

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L442)

```python
@property
def ceph_stable_release():
```

Retrieve ceph stable realease based on ansible config (jewel, luminous, etc.)

#### Returns

- `str` - Ceph stable release

### Ceph().check_health

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L517)

```python
def check_health(client=None, timeout=300):
```

Check if ceph is in healthy state

#### Arguments

- `client(CephObject)` - ceph object with ceph-common and ceph-keyring
- `timeout` *int* - max time to check if cluster is not healthy within timeout period - return 1

#### Returns

- `int` - return 0 when ceph is in healthy state, else 1

### Ceph().create_rbd_pool

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L643)

```python
def create_rbd_pool(k_and_m):
```

Generate pools for later testing use

#### Arguments

- `k_and_m(bool)` - ec-pool-k-m settings

### Ceph().distribute_all_yml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L573)

```python
def distribute_all_yml():
```

Distributes ansible all.yml config across all installers

### Ceph().generate_ansible_inventory

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L184)

```python
def generate_ansible_inventory(
    device_to_add=None,
    mixed_lvm_confs=None,
    filestore=False,
):
```

Generate ansible inventory file content for given cluster

#### Arguments

- `device_to_add(str)` - To add new osd to the cluster, default None
- `mixed_lvm_confs(str)` - To configure multiple mixed lvm configs, default None
- `filestore(bool)` - True for filestore usage, dafault False

#### Returns

- `str` - inventory

### Ceph.generate_repository_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L691)

```python
@staticmethod
def generate_repository_file(base_url, repos):
```

Generate rhel repository file for given repos

#### Arguments

- `base_url(str)` - rhel compose url
- `repos(list)` - repos behind compose/ to process

#### Returns

- `str` - repository file content

### Ceph().get_ansible_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L394)

```python
def get_ansible_config():
```

Get Ansible config settings for all.yml

#### Returns

- `dict` - Ansible config

### Ceph().get_ceph_demons

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L355)

```python
def get_ceph_demons(role=None):
```

Get Ceph demons list

#### Returns

- `list` - list of CephDemon

### Ceph().get_ceph_object

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L118)

```python
def get_ceph_object(role, order_id=0):
```

Returns single ceph object. If order id is provided returns that occurrence from results list, otherwise returns
first occurrence

#### Arguments

- `role(str)` - Ceph object's role
- `order_id(int)` - order number of the ceph object

#### Returns

- `CephObject` - ceph object

### Ceph().get_ceph_objects

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L102)

```python
def get_ceph_objects(role=None):
```

Get Ceph Object by role. Returns all objects if role is not defined. Ceph object can be Ceph demon, client,
installer or generic entity. Pool role is never assigned to Ceph object and means that node has no Ceph objects

#### Arguments

- `role` *str* - Ceph object's role as str

#### Returns

- `list` - ceph objects

### Ceph.get_iso_file_url

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L673)

```python
@staticmethod
def get_iso_file_url(base_url):
```

Retrurns iso url for given compose link

#### Arguments

- `base_url(str)` - rhel compose

#### Returns

- `str` - iso file url

### Ceph().get_metadata_list

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L451)

```python
def get_metadata_list(role, client=None):
```

Returns metadata for demons of specified role

#### Arguments

- `role(str)` - ceph demon role
- `client(CephObject)` - Client with keyring and ceph-common

#### Returns

- `list` - metadata as json object representation

### Ceph().get_node_by_hostname

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L784)

```python
def get_node_by_hostname(hostname):
```

Returns Ceph node by it's hostname

#### Arguments

- `hostname` *str* - hostname

### Ceph().get_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L85)

```python
def get_nodes(role=None, ignore=None):
```

Get node(s) by role. Return all nodes if role is not defined

#### Arguments

role (str, RolesContainer): node's role. Takes precedence over ignore
ignore (str, RolesContainer): node's role to ignore from the list

#### Returns

- `list` - nodes

### Ceph().get_osd_by_id

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L728)

```python
def get_osd_by_id(osd_id, client=None):
```

#### Arguments

osd_id:
client:

#### Returns

CephDemon:

### Ceph().get_osd_container_name_by_id

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L717)

```python
def get_osd_container_name_by_id(osd_id, client=None):
```

#### Arguments

osd_id:
client:

### Ceph().get_osd_data_partition

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L813)

```python
def get_osd_data_partition(osd_id, client=None):
```

Returns data partition by given osd id

#### Arguments

- `osd_id` *int* - osd id
- `client` *CephObject* - client, optional

#### Returns

- `str` - data path

### Ceph().get_osd_data_partition_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L793)

```python
def get_osd_data_partition_path(osd_id, client=None):
```

Returns data partition path by given osd id

#### Arguments

- `osd_id` *int* - osd id
- `client` *CephObject* - client, optional

#### Returns

- `str` - data partition path

### Ceph().get_osd_device

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L765)

```python
def get_osd_device(osd_id, client=None):
```

#### Arguments

osd_id:
client:

### Ceph().get_osd_devices

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L310)

```python
def get_osd_devices(node):
```

Get osd devices list

#### Arguments

- `node(CephNode)` - Ceph node with osd demon

#### Returns

- `list` - devices

### Ceph().get_osd_metadata

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L468)

```python
def get_osd_metadata(osd_id, client=None):
```

Retruns metadata for osd by given id

#### Arguments

- `osd_id(int)` - osd id
- `client(CephObject)` - Client with keyring and ceph-common

#### Returns

- `dict` - osd metadata like:
     {
        - `"id"` - 8,
        - `"arch"` - "x86_64",
        - `"back_addr"` - "172.16.115.29:6801/1672",
        - `"back_iface"` - "eth0",
        - `"backend_filestore_dev_node"` - "vdd",
        - `"backend_filestore_partition_path"` - "/dev/vdd1",
        - `"ceph_version"` - "ceph version 12.2.5-42.el7cp (82d52d7efa6edec70f6a0fc306f40b89265535fb) luminous
                (stable)",
        - `"cpu"` - "Intel(R) Xeon(R) CPU E5-2690 v3 @ 2.60GHz",
        - `"default_device_class"` - "hdd",
        - `"distro"` - "rhel",
        - `"distro_description"` - "Red Hat Enterprise Linux",
        - `"distro_version"` - "7.5",
        - `"filestore_backend"` - "xfs",
        - `"filestore_f_type"` - "0x58465342",
        - `"front_addr"` - "172.16.115.29:6800/1672",
        - `"front_iface"` - "eth0",
        - `"hb_back_addr"` - "172.16.115.29:6802/1672",
        - `"hb_front_addr"` - "172.16.115.29:6803/1672",
        - `"hostname"` - "ceph-shmohan-1537910194970-node2-osd",
        - `"journal_rotational"` - "1",
        - `"kernel_description"` - "#1 SMP Wed Mar 21 18:14:51 EDT 2018",
        - `"kernel_version"` - "3.10.0-862.el7.x86_64",
        - `"mem_swap_kb"` - "0",
        - `"mem_total_kb"` - "3880928",
        - `"os"` - "Linux",
        - `"osd_data"` - "/var/lib/ceph/osd/ceph-8",
        - `"osd_journal"` - "/var/lib/ceph/osd/ceph-8/journal",
        - `"osd_objectstore"` - "filestore",
        - `"rotational"` - "1"
     }

### Ceph().get_osd_service_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L745)

```python
def get_osd_service_name(osd_id, client=None):
```

#### Arguments

osd_id:
client:

### Ceph().refresh_ansible_config_from_all_yml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L582)

```python
def refresh_ansible_config_from_all_yml(installer=None):
```

Refreshes ansible config based on installer all.yml content

#### Arguments

- `installer(CephInstaller)` - Ceph installer. Will use first available installer if omitted

### Ceph().rhcs_version

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L68)

```python
@property
def rhcs_version():
```

Get rhcs version, will return DEFAULT_RHCS_VERSION if not set

#### Returns

- `LooseVersion` - rhcs version of given cluster

### Ceph().rhcs_version

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L78)

```python
@rhcs_version.setter
def rhcs_version(version):
```

### Ceph().set_ansible_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L369)

```python
def set_ansible_config(ansible_config):
```

Set ansible config for all.yml

#### Arguments

- `ansible_config(dict)` - Ceph Ansible all.yml config

### Ceph().setup_ceph_firewall

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L135)

```python
def setup_ceph_firewall():
```

Open required ports on nodes based on relevant ceph demons types

### Ceph().setup_insecure_registry

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L415)

```python
def setup_insecure_registry():
```

Update all ceph demons nodes to allow insecure registry use

### Ceph().setup_osd_devices

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L339)

```python
def setup_osd_devices(devices, node):
```

Sets osd devices on a node

#### Arguments

- `devices` *list* - list of devices (/dev/vdb, /dev/vdc)
- `node` *CephNode* - Ceph node

### Ceph().setup_packages

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L592)

```python
def setup_packages(
    base_url,
    hotfix_repo,
    installer_url,
    ubuntu_repo,
    build=None,
):
```

Setup packages required for ceph-ansible istallation

#### Arguments

- `base_url` *str* - rhel compose url
- `hotfix_repo` *str* - hotfix repo to use with priority
- `installer_url` *str* - installer url
- `ubuntu_repo` *str* - deb repo url
- `build` *str* - ceph-ansible build as numeric

### Ceph().setup_ssh_keys

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L155)

```python
def setup_ssh_keys():
```

Generate and distribute ssh keys within cluster

## CephClient

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1642)

```python
class CephClient(CephObject):
    def __init__(role, node):
```

#### See also

- [CephObject](#cephobject)

## CephDemon

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1573)

```python
class CephDemon(CephObject):
    def __init__(role, node):
```

#### See also

- [CephObject](#cephobject)

### CephDemon().ceph_demon_by_container_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1613)

```python
def ceph_demon_by_container_name(container_name):
```

### CephDemon().container_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1586)

```python
@property
def container_name():
```

### CephDemon().container_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1591)

```python
@container_name.setter
def container_name(name):
```

### CephDemon().container_prefix

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1595)

```python
@property
def container_prefix():
```

### CephDemon().exec_command

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1600)

```python
def exec_command(cmd, **kw):
```

Proxy to node's exec_command with wrapper to run commands inside the container for containerized demons

#### Arguments

- `cmd(str)` - command to execute
- `**kw` - options

#### Returns

node's exec_command resut

## CephInstaller

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1653)

```python
class CephInstaller(CephObject):
    def __init__(role, node):
```

#### See also

- [CephObject](#cephobject)

### CephInstaller().add_iscsi_settings

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1771)

```python
def add_iscsi_settings(test_data):
```

Add iscsi config to iscsigws.yml

#### Arguments

- `test_data` - test data dict

### CephInstaller().append_to_all_yml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1664)

```python
def append_to_all_yml(content):
```

Adds content to all.yml

#### Arguments

- `content(str)` - all.yml config as yml string

### CephInstaller().get_all_yml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1675)

```python
def get_all_yml():
```

Returns all.yml content

#### Returns

- `dict` - all.yml content

### CephInstaller().get_installed_ceph_versions

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1687)

```python
def get_installed_ceph_versions():
```

Returns installed ceph versions

#### Returns

- `str` - ceph vsersions

### CephInstaller().install_ceph_ansible

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1737)

```python
def install_ceph_ansible(rhbuild, **kw):
```

Installs ceph-ansible

### CephInstaller().setup_ansible_site_yml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1721)

```python
def setup_ansible_site_yml(containerized):
```

Create proper site.yml from sample for containerized or non-containerized deployment

#### Arguments

- `containerized(bool)` - use site-docker.yml.sample if True else site.yml.sample

### CephInstaller().write_inventory_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1700)

```python
def write_inventory_file(inventory_config):
```

Write inventory to hosts file for ansible use. Old file will be overwritten

#### Arguments

inventory_config(str):invnetory config compatible with ceph-ansible

## CephNode

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L953)

```python
class CephNode(object, object):
    def __init__(**kw):
```

### CephNode().chk_lvm_exists

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1471)

```python
def chk_lvm_exists():
```

### CephNode().connect

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1021)

```python
def connect():
```

connect to ceph instance using paramiko ssh protocol
eg: self.connect()
- setup tcp keepalive to max retries for active connection
- set up hostname and shortname as attributes for tests to query

### CephNode().create_ceph_object

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1205)

```python
def create_ceph_object(role):
```

Create ceph object on the node

#### Arguments

- `role(str)` - ceph object role

#### Returns

- `CephObject|CephDemon` - created ceph object

### CephNode().create_lvm

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1414)

```python
def create_lvm(devices, num=None, check_lvm=True):
```

Creates lvm volumes and returns device list suitable for ansible config

#### Arguments

- `devices` - list of devices
- `num` - number to concatenate with pv,vg and lv names
- `check_lvm` - To check if lvm exists is optional, by default checking is enabled

- `Returns` *list* - lvm volumes list

### CephNode().exec_command

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1087)

```python
def exec_command(**kw):
```

execute a command on the vm
eg: self.exec_cmd(cmd='uptime')
    or
    self.exec_cmd(cmd='background_cmd', check_ec=False)

#### Attributes

- `check_ec` - False will run the command and not wait for exit code

### CephNode().generate_id_rsa

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1075)

```python
def generate_id_rsa():
```

generate id_rsa key files for the new vm node

### CephNode().get_allocated_volumes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1006)

```python
def get_allocated_volumes():
```

### CephNode().get_ceph_demons

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1009)

```python
def get_ceph_demons(role=None):
```

Get Ceph demons list. Only active (those which will be part of the cluster) demons are shown.

#### Returns

- `list` - list of CephDemon

### CephNode().get_ceph_objects

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1193)

```python
def get_ceph_objects(role=None):
```

Get Ceph objects list on the node

#### Arguments

- `role(str)` - Ceph object role

#### Returns

- `list` - ceph objects

### CephNode().get_free_volumes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1003)

```python
def get_free_volumes():
```

### CephNode().install_lvm_util

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1479)

```python
def install_lvm_util():
```

Installs lvm util

### CephNode().multiple_lvm_scenarios

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1489)

```python
def multiple_lvm_scenarios(devices, scenario):
```

Creates lvm volumes,generates osd scenarios and returns dict, suitable for ansible config

#### Arguments

    - `devices` *list* - device list
    - `scenario` *func* - osd scenario to be generated
- `Returns` *dict* - generated osd scenario

### CephNode().obtain_root_permissions

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1406)

```python
def obtain_root_permissions(path):
```

Transfer ownership of root to current user for the path given. Recursive.

#### Arguments

- `path(str)` - file path

### CephNode().open_firewall_port

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1228)

```python
def open_firewall_port(port, protocol):
```

Opens firewall port on the node

#### Arguments

- `port(str)` - port, can be range
- `protocol(str)` - protcol

### CephNode().reconnect

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1169)

```python
def reconnect():
```

### CephNode().remove_ceph_object

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1218)

```python
def remove_ceph_object(ceph_object):
```

Removes ceph object form the node

#### Arguments

- `ceph_object(CephObject)` - ceph object to remove

### CephNode().role

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L999)

```python
@property
def role():
```

### CephNode().search_ethernet_interface

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1259)

```python
def search_ethernet_interface(ceph_node_list):
```

Search interface on the given node node which allows every node in the cluster accesible by it's shortname.

#### Arguments

- `ceph_node_list` *list* - lsit of CephNode

#### Returns

- `eth_interface` *str* - retturns None if no suitable interface found

### CephNode().set_eth_interface

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1069)

```python
def set_eth_interface(eth_interface):
```

set the eth interface

### CephNode().set_internal_ip

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1061)

```python
def set_internal_ip():
```

set the internal ip of the vm which differs from floating ip

### CephNode().setup_deb_cdn_repos

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1303)

```python
def setup_deb_cdn_repos(build):
```

Setup cdn repositories for deb systems

#### Arguments

- `build(str|LooseVersion)` - rhcs version

### CephNode().setup_deb_repos

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1354)

```python
def setup_deb_repos(deb_repo):
```

Setup repositories for deb system

#### Arguments

- `deb_repo(str)` - deb (Ubuntu) repository link

### CephNode().setup_rhel_cdn_repos

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1319)

```python
def setup_rhel_cdn_repos(build):
```

Setup cdn repositories for rhel systems

#### Arguments

- `build(str|LooseVersion)` - rhcs version

### CephNode().setup_rhel_repos

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1380)

```python
def setup_rhel_repos(base_url, installer_url=None):
```

Setup repositories for rhel

#### Arguments

- `base_url` *str* - compose url for rhel
- `installer_url` *str* - installer repos url

### CephNode().write_docker_daemon_json

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1291)

```python
def write_docker_daemon_json(json_text):
```

Write given string to /etc/docker/daemon/daemon

#### Arguments

- `json_text` *str* - json as string

### CephNode().write_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1153)

```python
def write_file(**kw):
```

## CephObject

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1534)

```python
class CephObject(object):
    def __init__(role, node):
```

### CephObject().exec_command

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1549)

```python
def exec_command(cmd, **kw):
```

Proxy to node's exec_command

#### Arguments

- `cmd(str)` - command to execute
- `**kw` - options

#### Returns

node's exec_command result

### CephObject().pkg_type

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1545)

```python
@property
def pkg_type():
```

### CephObject().write_file

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1561)

```python
def write_file(**kw):
```

Proxy to node's write file

#### Arguments

- `**kw` - options

#### Returns

node's write_file result

## CephObjectFactory

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1785)

```python
class CephObjectFactory(object):
    def __init__(node):
```

### CephObjectFactory().create_ceph_object

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1797)

```python
def create_ceph_object(role):
```

Create an appropriate Ceph object by role

#### Arguments

- `role` - role string

#### Returns

Ceph object based on role

## CephOsd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1617)

```python
class CephOsd(CephDemon):
    def __init__(node, device=None):
```

#### See also

- [CephDemon](#cephdemon)

### CephOsd().container_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1628)

```python
@property
def container_name():
```

### CephOsd().is_active

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1633)

```python
@property
def is_active():
```

### CephOsd().is_active

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L1637)

```python
@is_active.setter
def is_active(value):
```

## NodeVolume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L890)

```python
class NodeVolume(object):
    def __init__(status):
```

## RolesContainer

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L828)

```python
class RolesContainer(object):
    def __init__(role='pool'):
```

Container for single or multiple node roles.
Can be used as iterable or with equality '==' operator to check if role is present for the node.
Note that '==' operator will behave the same way as 'in' operator i.e. check that value is present in the role list.

### RolesContainer().append

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L874)

```python
def append(object):
```

### RolesContainer().clear

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L886)

```python
def clear():
```

### RolesContainer().equals

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L850)

```python
def equals(other):
```

### RolesContainer().extend

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L877)

```python
def extend(iterable):
```

### RolesContainer().remove

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L871)

```python
def remove(object):
```

### RolesContainer().update_role

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L881)

```python
def update_role(roles_list):
```

## SSHConnectionManager

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L898)

```python
class SSHConnectionManager(object):
    def __init__(
        ip_address,
        username,
        password,
        look_for_keys=False,
        outage_timeout=300,
    ):
```

### SSHConnectionManager().client

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L910)

```python
@property
def client():
```

### SSHConnectionManager().get_client

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L914)

```python
def get_client():
```

### SSHConnectionManager().get_transport

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L942)

```python
def get_transport():
```

### SSHConnectionManager().transport

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/ceph.py#L938)

```python
@property
def transport():
```
