# Openshift Ops

> Auto-generated documentation for [ocs_ci.ocs.openshift_ops](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Openshift Ops
    - [OCP](#ocp)
        - [OCP.call_api](#ocpcall_api)
        - [OCP().create_project](#ocpcreate_project)
        - [OCP().get_labels](#ocpget_labels)
        - [OCP().get_pods](#ocpget_pods)
        - [OCP().get_projects](#ocpget_projects)
        - [OCP().get_services](#ocpget_services)
        - [OCP().get_services_in_namespace](#ocpget_services_in_namespace)
        - [OCP.set_kubeconfig](#ocpset_kubeconfig)

## OCP

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L14)

```python
class OCP(object):
    def __init__():
```

Class which contains various utility functions for interacting
with OpenShift

### OCP.call_api

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L41)

```python
@staticmethod
def call_api(method, **kw):
```

This function makes generic REST calls

#### Arguments

- `method(str)` - one of the GET, CREATE, PATCH, POST, DELETE
- `**kw` - Based on context of the call kw will be populated by caller

#### Returns

ResourceInstance object

### OCP().create_project

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L193)

```python
def create_project(project):
```

Creates new project

#### Arguments

- `project` *str* - project name

#### Returns

- `bool` - True if successful otherwise False

### OCP().get_labels

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L92)

```python
def get_labels(pod_name, pod_namespace):
```

Get labels from specific pod

#### Arguments

- `pod_name` *str* - Name of pod in oc cluster
- `pod_namespace` *str* - pod namespace in which the pod lives

#### Raises

- `NotFoundError` - If resource not found

#### Returns

- `dict` - All the openshift labels on a given pod

### OCP().get_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L67)

```python
def get_pods(**kw):
```

Get pods in specific namespace or across oc cluster.

#### Arguments

- `**kw` - ex: namespace=rook-ceph, label_selector='x==y'

#### Returns

- `list` - of pods names, if no namespace provided then this function
    returns all pods across openshift cluster.

### OCP().get_projects

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L154)

```python
def get_projects():
```

Gets all the projects in the cluster

#### Returns

- `list` - List of projects

### OCP().get_services

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L165)

```python
def get_services():
```

Gets all the services in the cluster

#### Returns

- `dict` - defaultdict of services, key represents the namespace
      and value represents the services

### OCP().get_services_in_namespace

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L182)

```python
def get_services_in_namespace(namespace):
```

Gets the services in a namespace

#### Returns

- `list` - list of services in a namespace

### OCP.set_kubeconfig

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/openshift_ops.py#L126)

```python
@staticmethod
def set_kubeconfig(kubeconfig_path):
```

Export environment variable KUBECONFIG for future calls of OC commands
or other API calls

#### Arguments

- `kubeconfig_path` *str* - path to kubeconfig file to be exported

#### Returns

- `boolean` - True if successfully connected to cluster, False otherwise
