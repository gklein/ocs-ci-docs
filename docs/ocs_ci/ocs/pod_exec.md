# Pod Exec

> Auto-generated documentation for [ocs_ci.ocs.pod_exec](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/pod_exec.py) module.

Dispatcher for proper exec based on api-client config

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Pod Exec
    - [Exec](#exec)
        - [Exec().run](#execrun)
    - [KubClient](#kubclient)
        - [KubClient().run](#kubclientrun)
    - [register_class](#register_class)

This class takes care of dispatching a proper api-client instance
to take care of command execution.

WHY this class ?
Execution of command might happen using various means, as of now we are using
kubernetes client but we might also use openshift rest client. To cope with
this we might have to dynamically figure out at run time which backend to use.

This module will have all api client class definitions in this file along with
dispatcher class Exec.

## Exec

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/pod_exec.py#L61)

```python
class Exec(object):
    def __init__(oc_client='KubClient'):
```

Dispatcher class for proper api client instantiation

This class has a factory function which returns proper api client instance
necessary for command execution

### Exec().run

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/pod_exec.py#L71)

```python
def run(podname, namespace, cmd_obj):
```

 actual run happens here
Command will be fwd to api client object
and it should return a 3 tuple
(stdout, stderr, retval)

## KubClient

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/pod_exec.py#L84)

```python
register_class
class KubClient(object):
    def __init__():
```

Specific to upstream Kubernetes client library

#### See also

- [register_class](#register_class)

### KubClient().run

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/pod_exec.py#L101)

```python
def run(podname, namespace, cmd_obj):
```

## register_class

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/pod_exec.py#L49)

```python
def register_class(cls):
```

Decorator for registering a class 'cls' in class map

Please make sure that api-client name in config should be same as
class name.
