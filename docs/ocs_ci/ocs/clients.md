# Clients

> Auto-generated documentation for [ocs_ci.ocs.clients](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Clients
    - [WinNode](#winnode)
        - [WinNode().check_disk](#winnodecheck_disk)
        - [WinNode().connect_to_target](#winnodeconnect_to_target)
        - [WinNode().create_disk](#winnodecreate_disk)
        - [WinNode().create_fio_job_options](#winnodecreate_fio_job_options)
        - [WinNode().create_new_target](#winnodecreate_new_target)
        - [WinNode().delete_target](#winnodedelete_target)
        - [WinNode().disconnect_from_target](#winnodedisconnect_from_target)
        - [WinNode().get_iscsi_initiator_name](#winnodeget_iscsi_initiator_name)
        - [WinNode().run_fio_test](#winnoderun_fio_test)
        - [WinNode().start_iscsi_initiator](#winnodestart_iscsi_initiator)
        - [WinNode().win_exec](#winnodewin_exec)

## WinNode

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L11)

```python
class WinNode(object):
    def __init__(**kw):
```

### WinNode().check_disk

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L77)

```python
def check_disk(number):
```

### WinNode().connect_to_target

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L58)

```python
def connect_to_target(ip, username, password):
```

### WinNode().create_disk

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L69)

```python
def create_disk(number):
```

### WinNode().create_fio_job_options

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L81)

```python
def create_fio_job_options(job_options):
```

### WinNode().create_new_target

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L51)

```python
def create_new_target(ip, port=3260):
```

### WinNode().delete_target

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L55)

```python
def delete_target():
```

### WinNode().disconnect_from_target

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L64)

```python
def disconnect_from_target():
```

### WinNode().get_iscsi_initiator_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L46)

```python
def get_iscsi_initiator_name():
```

### WinNode().run_fio_test

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L85)

```python
def run_fio_test():
```

### WinNode().start_iscsi_initiator

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L42)

```python
def start_iscsi_initiator():
```

### WinNode().win_exec

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/clients.py#L19)

```python
def win_exec(ps_command, timeout=180):
```
