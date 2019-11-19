# Rados Utils

> Auto-generated documentation for [ocs_ci.ocs.rados_utils](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Rados Utils
    - [RadosHelper](#radoshelper)
        - [RadosHelper().create_pool](#radoshelpercreate_pool)
        - [RadosHelper().get_mgr_proxy_container](#radoshelperget_mgr_proxy_container)
        - [RadosHelper().get_num_pools](#radoshelperget_num_pools)
        - [RadosHelper().get_osd_dump_json](#radoshelperget_osd_dump_json)
        - [RadosHelper().get_pg_primary](#radoshelperget_pg_primary)
        - [RadosHelper().get_pg_random](#radoshelperget_pg_random)
        - [RadosHelper().get_pgid](#radoshelperget_pgid)
        - [RadosHelper().get_pool_dump](#radoshelperget_pool_dump)
        - [RadosHelper().get_pool_num](#radoshelperget_pool_num)
        - [RadosHelper().get_pool_property](#radoshelperget_pool_property)
        - [RadosHelper().is_up](#radoshelperis_up)
        - [RadosHelper().kill_osd](#radoshelperkill_osd)
        - [RadosHelper().list_pools](#radoshelperlist_pools)
        - [RadosHelper().raw_cluster_cmd](#radoshelperraw_cluster_cmd)
        - [RadosHelper().revive_osd](#radoshelperrevive_osd)

## RadosHelper

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L10)

```python
class RadosHelper():
    def __init__(mon, config=None, log=None, cluster='ceph'):
```

### RadosHelper().create_pool

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L59)

```python
def create_pool(
    pool_name,
    pg_num=16,
    erasure_code_profile_name=None,
    min_size=None,
    erasure_code_use_overwrites=False,
):
```

Create a pool named from the pool_name parameter.

#### Arguments

- `pool_name` - name of the pool being created.
- `pg_num` - initial number of pgs.
- `erasure_code_profile_name` - if set and !None create an
    erasure coded pool using the profile
- `erasure_code_use_overwrites` - if true, allow overwrites

### RadosHelper().get_mgr_proxy_container

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L224)

```python
def get_mgr_proxy_container(node, docker_image, proxy_container='mgr_proxy'):
```

Returns mgr dummy container to access containerized storage

#### Arguments

- `node` *ceph.ceph.CephNode* - ceph node
- `docker_image(str)` - repository/image:tag

#### Returns

- `ceph.ceph.CephDemon` - mgr object

### RadosHelper().get_num_pools

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L42)

```python
def get_num_pools():
```

#### Returns

number of pools in the
        cluster

### RadosHelper().get_osd_dump_json

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L49)

```python
def get_osd_dump_json():
```

osd dump --format=json converted to a python object

#### Returns

the python object

### RadosHelper().get_pg_primary

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L152)

```python
def get_pg_primary(pool, pgnum):
```

get primary for pool, pgnum (e.g. (data, 0)->0

### RadosHelper().get_pg_random

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L163)

```python
def get_pg_random(pool, pgnum):
```

get random osd for pool, pgnum (e.g. (data, 0)->0

### RadosHelper().get_pgid

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L140)

```python
def get_pgid(pool, pgnum):
```

#### Arguments

- `pool` - pool name
- `pgnum` - pg number

#### Returns

a string representing this pg.

### RadosHelper().get_pool_dump

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L124)

```python
def get_pool_dump(pool):
```

get the osd dump part of a pool

### RadosHelper().get_pool_num

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L134)

```python
def get_pool_num(pool):
```

get number for pool (e.g., data -> 2)

### RadosHelper().get_pool_property

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L107)

```python
def get_pool_property(pool_name, prop):
```

#### Arguments

- `pool_name` - pool
- `prop` - property to be checked.

#### Returns

property as an int value.

### RadosHelper().is_up

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L192)

```python
def is_up(osd_id):
```

:return 1 if up, 0 if down

### RadosHelper().kill_osd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L174)

```python
def kill_osd(osd_node, osd_service):
```

:params: id , type of signal, list of osd objects
    type: "SIGKILL", "SIGTERM", "SIGHUP" etc.

#### Returns

1 or 0

### RadosHelper().list_pools

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L99)

```python
def list_pools():
```

list all pool names

### RadosHelper().raw_cluster_cmd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L24)

```python
def raw_cluster_cmd(*args):
```

#### Returns

(stdout, stderr)

### RadosHelper().revive_osd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/rados_utils.py#L205)

```python
def revive_osd(osd_node, osd_service):
```

#### Returns

0 if revive success,1 if fail
