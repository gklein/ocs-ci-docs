# Aws

> Auto-generated documentation for [ocs_ci.deployment.aws](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py) module.

This module contains platform specific methods and classes for deployment
on AWS platform

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Deployment](index.md#deployment) / Aws
    - [AWSIPI](#awsipi)
        - [AWSIPI().deploy](#awsipideploy)
        - [AWSIPI().deploy_ocp](#awsipideploy_ocp)
        - [AWSIPI().destroy_cluster](#awsipidestroy_cluster)
    - [AWSUPI](#awsupi)
        - [AWSUPI().deploy](#awsupideploy)
        - [AWSUPI().deploy_ocp](#awsupideploy_ocp)
        - [AWSUPI().deploy_prereq](#awsupideploy_prereq)
        - [AWSUPI().destroy_cluster](#awsupidestroy_cluster)

## AWSIPI

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L198)

```python
class AWSIPI(AWSBase, BaseOCPDeployment):
    def __init__():

    def __init__():
```

A class to handle AWS IPI specific deployment

#### See also

- [AWSBase](#awsbase)
- [OCPDeployment](ocp.md#ocpdeployment)

### AWSIPI().deploy

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L210)

```python
def deploy(log_cli_level='DEBUG'):
```

Deployment specific to OCP cluster on this platform

#### Arguments

- `log_cli_level` *str* - openshift installer's log level
    - `(default` - "DEBUG")

### AWSIPI().deploy_ocp

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L229)

```python
def deploy_ocp(log_cli_level='DEBUG'):
```

Deployment specific to OCP cluster on this platform

#### Arguments

- `log_cli_level` *str* - openshift installer's log level
    - `(default` - "DEBUG")

### AWSIPI().destroy_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L249)

```python
def destroy_cluster(log_level='DEBUG'):
```

Destroy OCP cluster specific to AWS IPI

#### Arguments

- `log_level` *str* - log level openshift-installer (default: DEBUG)

## AWSUPI

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L260)

```python
class AWSUPI(AWSBase, BaseOCPDeployment):
    def __init__():

    def __init__():
```

A class to handle AWS UPI specific deployment

#### See also

- [AWSBase](#awsbase)
- [OCPDeployment](ocp.md#ocpdeployment)

### AWSUPI().deploy

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L331)

```python
def deploy(log_cli_level='DEBUG'):
```

Exact deployment will happen here

#### Arguments

- `log_cli_level` *str* - openshift installer's log level
    - `(default` - "DEBUG")

### AWSUPI().deploy_ocp

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L387)

```python
def deploy_ocp(log_cli_level='DEBUG'):
```

OCP deployment specific to AWS UPI

#### Arguments

- `log_cli_level` *str* - openshift installer's log level
   - `(default` - 'DEBUG')

### AWSUPI().deploy_prereq

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L282)

```python
def deploy_prereq():
```

Overriding deploy_prereq from parent. Perform all necessary
prerequisites for AWSUPI here.

### AWSUPI().destroy_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/aws.py#L399)

```python
def destroy_cluster(log_level='DEBUG'):
```

Destroy OCP cluster for AWS UPI

#### Arguments

- `log_level` *str* - log level for openshift-installer (
    default:DEBUG)
