# Deployment

> Auto-generated documentation for [ocs_ci.deployment.deployment](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py) module.

This module provides base class for different deployment
platforms like AWS, VMWare, Baremetal etc.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Deployment](index.md#deployment) / Deployment
    - [Deployment](#deployment)
        - [Deployment().add_node](#deploymentadd_node)
        - [Deployment().add_volume](#deploymentadd_volume)
        - [Deployment().deploy_cluster](#deploymentdeploy_cluster)
        - [Deployment().deploy_ocp](#deploymentdeploy_ocp)
        - [Deployment().deploy_ocs](#deploymentdeploy_ocs)
        - [Deployment().deploy_ocs_via_operator](#deploymentdeploy_ocs_via_operator)
        - [Deployment().destroy_cluster](#deploymentdestroy_cluster)
        - [Deployment.get_olm_and_subscription_manifest](#deploymentget_olm_and_subscription_manifest)
        - [Deployment().label_and_taint_nodes](#deploymentlabel_and_taint_nodes)
        - [Deployment().patch_default_sc_to_non_default](#deploymentpatch_default_sc_to_non_default)

## Deployment

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L39)

```python
class Deployment(object, BaseOCPDeployment):
    def __init__():
```

Base for all deployment platforms

#### See also

- [OCPDeployment](ocp.md#ocpdeployment)

### Deployment().add_node

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L410)

```python
def add_node():
```

Implement platform-specific add_node in child class

### Deployment().add_volume

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L56)

```python
def add_volume():
```

Implement add_volume in child class which is specific to
platform

### Deployment().deploy_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L63)

```python
def deploy_cluster(log_cli_level='DEBUG'):
```

We are handling both OCP and OCS deployment here based on flags

#### Arguments

- `log_cli_level` *str* - log level for installer (default: DEBUG)

### Deployment().deploy_ocp

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L96)

```python
def deploy_ocp(log_cli_level='DEBUG'):
```

Base deployment steps, the rest should be implemented in the child
class.

#### Arguments

- `log_cli_level` *str* - log level for installer (default: DEBUG)

### Deployment().deploy_ocs

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L296)

```python
def deploy_ocs():
```

Handle OCS deployment, since OCS deployment steps are common to any
platform, implementing OCS deployment here in base class.

### Deployment().deploy_ocs_via_operator

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L228)

```python
def deploy_ocs_via_operator():
```

Method for deploy OCS via OCS operator

### Deployment().destroy_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L399)

```python
def destroy_cluster(log_level='DEBUG'):
```

Base destroy cluster method, for more platform specific stuff please
overload this method in child class.

#### Arguments

- `log_level` *str* - log level for installer (default: DEBUG)

### Deployment.get_olm_and_subscription_manifest

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L175)

```python
@staticmethod
def get_olm_and_subscription_manifest():
```

This method prepare manifest for deploy OCS operator and subscription.

#### Returns

- `tuple` - Path to olm deploy and subscription manifest

### Deployment().label_and_taint_nodes

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L108)

```python
def label_and_taint_nodes():
```

Label and taint worker nodes to be used by OCS operator

### Deployment().patch_default_sc_to_non_default

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/deployment.py#L416)

```python
def patch_default_sc_to_non_default():
```

Patch storage class which comes as default with installation to non-default
