# Vmware

> Auto-generated documentation for [ocs_ci.deployment.vmware](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py) module.

This module contains platform specific methods and classes for deployment
on vSphere platform

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Deployment](index.md#deployment) / Vmware
    - [VSPHEREUPI](#vsphereupi)
        - [VSPHEREUPI().configure_storage_for_image_registry](#vsphereupiconfigure_storage_for_image_registry)
        - [VSPHEREUPI().convert_yaml2tfvars](#vsphereupiconvert_yaml2tfvars)
        - [VSPHEREUPI().create_config](#vsphereupicreate_config)
        - [VSPHEREUPI().create_ignitions](#vsphereupicreate_ignitions)
        - [VSPHEREUPI().deploy](#vsphereupideploy)
        - [VSPHEREUPI().deploy_ocp](#vsphereupideploy_ocp)
        - [VSPHEREUPI().deploy_prereq](#vsphereupideploy_prereq)
        - [VSPHEREUPI().destroy_cluster](#vsphereupidestroy_cluster)

## VSPHEREUPI

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L71)

```python
class VSPHEREUPI(VSPHEREBASE, BaseOCPDeployment):
    def __init__():

    def __init__():
```

A class to handle vSphere UPI specific deployment

#### See also

- [OCPDeployment](ocp.md#ocpdeployment)
- [VSPHEREBASE](#vspherebase)

### VSPHEREUPI().configure_storage_for_image_registry

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L289)

```python
def configure_storage_for_image_registry(kubeconfig):
```

Configures storage for the image registry

### VSPHEREUPI().convert_yaml2tfvars

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L217)

```python
def convert_yaml2tfvars(yaml):
```

Converts yaml file to tfvars. It creates the tfvars with the
same filename in the required format which is used for deployment.

#### Arguments

- `yaml` *str* - File path to yaml

#### Returns

- `str` - File path to tfvars

### VSPHEREUPI().create_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L253)

```python
def create_config():
```

Creates the OCP deploy config for the vSphere

### VSPHEREUPI().create_ignitions

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L279)

```python
def create_ignitions():
```

Creates the ignition files

### VSPHEREUPI().deploy

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L301)

```python
def deploy(log_cli_level='DEBUG'):
```

Deployment specific to OCP cluster on this platform

#### Arguments

- `log_cli_level` *str* - openshift installer's log level
    - `(default` - "DEBUG")

### VSPHEREUPI().deploy_ocp

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L347)

```python
def deploy_ocp(log_cli_level='DEBUG'):
```

Deployment specific to OCP cluster on vSphere platform

#### Arguments

- `log_cli_level` *str* - openshift installer's log level
    - `(default` - "DEBUG")

### VSPHEREUPI().deploy_prereq

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L96)

```python
def deploy_prereq():
```

Pre-Requisites for vSphere UPI Deployment

### VSPHEREUPI().destroy_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/vmware.py#L358)

```python
def destroy_cluster(log_level='DEBUG'):
```

Destroy OCP cluster specific to vSphere UPI

#### Arguments

- `log_level` *str* - log level openshift-installer (default: DEBUG)
