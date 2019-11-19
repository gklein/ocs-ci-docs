# Api Client

> Auto-generated documentation for [ocs_ci.ocs.api_client](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py) module.

A module for implementing specific api client for interacting with openshift or
kubernetes cluster

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Api Client
    - [APIClientBase](#apiclientbase)
        - [APIClientBase().api_create](#apiclientbaseapi_create)
        - [APIClientBase().api_delete](#apiclientbaseapi_delete)
        - [APIClientBase().api_get](#apiclientbaseapi_get)
        - [APIClientBase().api_patch](#apiclientbaseapi_patch)
        - [APIClientBase().api_post](#apiclientbaseapi_post)
        - [APIClientBase().create_service](#apiclientbasecreate_service)
        - [APIClientBase().get_labels](#apiclientbaseget_labels)
        - [APIClientBase().get_pods](#apiclientbaseget_pods)
        - [APIClientBase().name](#apiclientbasename)
    - [KubeClient](#kubeclient)
        - [KubeClient().name](#kubeclientname)
    - [OCCLIClient](#occliclient)
        - [OCCLIClient().name](#occliclientname)
    - [OCRESTClient](#ocrestclient)
        - [OCRESTClient().api_create](#ocrestclientapi_create)
        - [OCRESTClient().api_delete](#ocrestclientapi_delete)
        - [OCRESTClient().api_get](#ocrestclientapi_get)
        - [OCRESTClient().api_patch](#ocrestclientapi_patch)
        - [OCRESTClient().api_post](#ocrestclientapi_post)
        - [OCRESTClient().create_service](#ocrestclientcreate_service)
        - [OCRESTClient().get_labels](#ocrestclientget_labels)
        - [OCRESTClient().get_pods](#ocrestclientget_pods)
        - [OCRESTClient().name](#ocrestclientname)
    - [get_api_client](#get_api_client)

APIClientBase is an abstract base class which imposes a contract on
methods to be implemented in derived classes which are specific to api client

## APIClientBase

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L43)

```python
class APIClientBase():
```

Abstract base class for all api-client classes

This is an abstract base class and api-client specific classes
should implement all the methods for interacting with openshift cluster

### APIClientBase().api_create

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L73)

```python
@abstractmethod
def api_create():
```

### APIClientBase().api_delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L65)

```python
@abstractmethod
def api_delete():
```

### APIClientBase().api_get

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L57)

```python
@abstractmethod
def api_get():
```

### APIClientBase().api_patch

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L69)

```python
@abstractmethod
def api_patch():
```

### APIClientBase().api_post

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L61)

```python
@abstractmethod
def api_post():
```

### APIClientBase().create_service

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L114)

```python
@abstractmethod
def create_service(**kw):
```

Create an openshift service

#### Arguments

- `**kw` - ex body="content", namespace='ocnamespace'

#### Returns

- `dict` - Response from api server

- `Note` - Returns could be tricky because it varies from client to
client. If its oc-cli then extra work needs to be done in the
specific implementation.

### APIClientBase().get_labels

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L96)

```python
@abstractmethod
def get_labels(pod_name, pod_namespace):
```

Get the openshift labels on a given pod

#### Arguments

- `pod_name(str)` - Name of pod for which labels to be fetched
- `pod_namespace(str)` - namespace of pod where this pod lives

#### Raises

- `NotImplementedError` - if function not implemented by client

#### Returns

- `dict` - Labels associated with pod

### APIClientBase().get_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L77)

```python
@abstractmethod
def get_pods(**kwargs):
```

Because of discrepancies in IO format of each client api
leaving this to be implemented by specific client

#### Arguments

- `**kwargs` - ex: namespace='namespace',openshift namespace from
    which we need pods

#### Raises

- `NotImplementedError` - if client has not implemented this function.

#### Returns

- `pod_names` *list* - A list of pod names

### APIClientBase().name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L51)

```python
@property
@abstractmethod
def name():
```

Concrete class will have respective api-client name

## KubeClient

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L247)

```python
class KubeClient(APIClientBase):
```

All activities using upstream kubernetes python client

#### See also

- [APIClientBase](#apiclientbase)

### KubeClient().name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L252)

```python
@property
def name():
```

## OCCLIClient

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L234)

```python
class OCCLIClient(APIClientBase):
```

All activities using oc-cli.

This implements all functionalities like create, patch, delete using
oc commands.

#### See also

- [APIClientBase](#apiclientbase)

### OCCLIClient().name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L242)

```python
@property
def name():
```

## OCRESTClient

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L133)

```python
class OCRESTClient(APIClientBase):
    def __init__():
```

All activities using openshift REST client

#### See also

- [APIClientBase](#apiclientbase)

### OCRESTClient().api_create

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L230)

```python
def api_create(**kw):
```

### OCRESTClient().api_delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L224)

```python
def api_delete(**kw):
```

### OCRESTClient().api_get

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L218)

```python
def api_get(**kw):
```

### OCRESTClient().api_patch

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L227)

```python
def api_patch(**kw):
```

### OCRESTClient().api_post

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L221)

```python
def api_post(**kw):
```

### OCRESTClient().create_service

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L203)

```python
def create_service(**kw):
```

#### Arguments

- `kw` - ex: body={body} for the request which has service spec

#### Returns

ResourceInstance

### OCRESTClient().get_labels

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L170)

```python
def get_labels(pod_name, pod_namespace):
```

Get labels from a specific pod

#### Arguments

- `pod_name` *str* - Name of the pod
- `pod_namespace` *str* - namespace where this pod lives

#### Raises

- `NotFoundError` - If resource not found

#### Returns

- `dict` - All the labels on a pod

### OCRESTClient().get_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L144)

```python
def get_pods(**kwargs):
```

Get pods in specific namespace or across oc cluster

#### Arguments

- `**kwargs` - ex: namespace=rook-ceph, label_selector='x==y'

#### Returns

- `list` - of pods names,if no namespace provided then this function
    returns all pods across openshift cluster

### OCRESTClient().name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L140)

```python
@property
def name():
```

## get_api_client

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/api_client.py#L20)

```python
def get_api_client(client_name):
```

Get instance of corresponding api-client object with given name

#### Arguments

- `client_name` *str* - name of the api client to be instantiated

#### Returns

api client object
