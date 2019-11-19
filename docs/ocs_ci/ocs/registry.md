# Registry

> Auto-generated documentation for [ocs_ci.ocs.registry](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Registry
    - [add_role_to_user](#add_role_to_user)
    - [change_registry_backend_to_ocs](#change_registry_backend_to_ocs)
    - [enable_route_and_create_ca_for_registry_access](#enable_route_and_create_ca_for_registry_access)
    - [get_default_route_name](#get_default_route_name)
    - [get_oc_podman_login_cmd](#get_oc_podman_login_cmd)
    - [get_registry_pod_obj](#get_registry_pod_obj)
    - [get_registry_pvc](#get_registry_pvc)
    - [image_list_all](#image_list_all)
    - [image_pull](#image_pull)
    - [image_push](#image_push)
    - [image_rm](#image_rm)
    - [validate_pvc_mount_on_registry_pod](#validate_pvc_mount_on_registry_pod)
    - [validate_registry_pod_status](#validate_registry_pod_status)

## add_role_to_user

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L156)

```python
def add_role_to_user(role_type, user):
```

Function to add role to user

#### Arguments

- `role_type` *str* - Type of the role to be added
- `user` *str* - User to be added for the role

#### Raises

- `AssertionError` - When failure in adding new role to user

## change_registry_backend_to_ocs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L17)

```python
def change_registry_backend_to_ocs():
```

Function to deploy registry with OCS backend.

#### Raises

- `AssertionError` - When failure in change of registry backend to OCS

## enable_route_and_create_ca_for_registry_access

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L175)

```python
def enable_route_and_create_ca_for_registry_access():
```

Function to enable route and to create ca,
copy to respective location for registry access

#### Raises

- `AssertionError` - When failure in enabling registry default route

## get_default_route_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L142)

```python
def get_default_route_name():
```

Function to get default route name

#### Returns

- `route_name` *str* - Returns default route name

## get_oc_podman_login_cmd

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L79)

```python
def get_oc_podman_login_cmd():
```

Function to get oc and podman login commands on node

#### Returns

- `cmd_list` *list* - List of cmd for oc/podman login

## get_registry_pod_obj

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L47)

```python
def get_registry_pod_obj():
```

Function to get registry pod obj

#### Returns

- `pod_obj` *list* - List of Registry pod objs

#### Raises

- `UnexpectedBehaviour` - When image-registry pod is not present.

## get_registry_pvc

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L130)

```python
def get_registry_pvc():
```

Function to get registry pvc

#### Returns

- `pvc_name` *str* - Returns name of the OCS pvc backed for registry

## image_list_all

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L253)

```python
def image_list_all():
```

Function to list the images in the podman registry

#### Returns

- `image_list_output` *str* - Images present in cluster

## image_pull

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L211)

```python
def image_pull(image_url):
```

Function to pull images from repositories

#### Arguments

- `image_url` *str* - Image url container image repo link

## image_push

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L226)

```python
def image_push(image_url, namespace):
```

Function to push images to destination

#### Arguments

- `image_url` *str* - Image url container image repo link
- `namespace` *str* - Image to be uploaded namespace

#### Returns

- `registry_path` *str* - Uploaded image path

## image_rm

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L268)

```python
def image_rm(registry_path):
```

Function to remove images from registry

#### Arguments

- `registry_path` *str* - Image registry path

## validate_pvc_mount_on_registry_pod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L108)

```python
def validate_pvc_mount_on_registry_pod():
```

Function to validate pvc mounted on the registry pod

#### Raises

- `AssertionError` - When PVC mount not present in the registry pod

## validate_registry_pod_status

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/registry.py#L122)

```python
def validate_registry_pod_status():
```

Function to validate registry pod status
