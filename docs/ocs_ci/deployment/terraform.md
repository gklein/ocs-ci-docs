# Terraform

> Auto-generated documentation for [ocs_ci.deployment.terraform](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/terraform.py) module.

This module contains terraform specific methods and classes needed
for deployment on vSphere platform

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Deployment](index.md#deployment) / Terraform
    - [Terraform](#terraform)
        - [Terraform().apply](#terraformapply)
        - [Terraform().destroy](#terraformdestroy)
        - [Terraform().initialize](#terraforminitialize)

## Terraform

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/terraform.py#L12)

```python
class Terraform(object):
    def __init__(path):
```

Wrapper for terraform

### Terraform().apply

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/terraform.py#L35)

```python
def apply(tfvars, bootstrap_complete=False):
```

Apply the changes required to reach the desired state of the configuration

#### Arguments

- `tfvars` *str* - path to terraform.tfvars file
- `bootstrap_complete` *bool* - Removes bootstrap node if True

### Terraform().destroy

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/terraform.py#L50)

```python
def destroy(tfvars):
```

Destroys the cluster

#### Arguments

- `tfvars` *str* - path to terraform.tfvars file

### Terraform().initialize

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/terraform.py#L19)

```python
def initialize(upgrade=False):
```

Initialize a working directory containing Terraform configuration files

#### Arguments

- `upgrade` *bool* - True in case installing modules needs upgrade from
    previously-downloaded objects, False otherwise
