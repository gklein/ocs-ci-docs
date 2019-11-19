# Ocp

> Auto-generated documentation for [ocs_ci.deployment.ocp](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py) module.

This module provides base class for OCP deployment.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Deployment](index.md#deployment) / Ocp
    - [OCPDeployment](#ocpdeployment)
        - [OCPDeployment().create_config](#ocpdeploymentcreate_config)
        - [OCPDeployment().deploy](#ocpdeploymentdeploy)
        - [OCPDeployment().deploy_prereq](#ocpdeploymentdeploy_prereq)
        - [OCPDeployment().destroy](#ocpdeploymentdestroy)
        - [OCPDeployment().download_installer](#ocpdeploymentdownload_installer)
        - [OCPDeployment().get_pull_secret](#ocpdeploymentget_pull_secret)
        - [OCPDeployment().get_ssh_key](#ocpdeploymentget_ssh_key)
        - [OCPDeployment().test_cluster](#ocpdeploymenttest_cluster)

## OCPDeployment

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L22)

```python
class OCPDeployment():
    def __init__():
```

### OCPDeployment().create_config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L119)

```python
def create_config():
```

Create the OCP deploy config, if something needs to be changed fro
specific platform you can overload this method in child class.

### OCPDeployment().deploy

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L151)

```python
def deploy(log_cli_level='DEBUG'):
```

Implement ocp deploy in specific child class

### OCPDeployment().deploy_prereq

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L83)

```python
def deploy_prereq():
```

Perform generic prereq before calling openshift-installer
This method performs all the basic steps necessary before invoking the
installer

### OCPDeployment().destroy

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L169)

```python
def destroy(log_level='DEBUG'):
```

Destroy OCP cluster specific

#### Arguments

- `log_level` *str* - log level openshift-installer (default: DEBUG)

### OCPDeployment().download_installer

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L34)

```python
def download_installer():
```

Method to download installer

#### Returns

- `str` - path to the installer

### OCPDeployment().get_pull_secret

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L50)

```python
def get_pull_secret():
```

Load pull secret file

#### Returns

- `dict` - content of pull secret

### OCPDeployment().get_ssh_key

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L68)

```python
def get_ssh_key():
```

Loads public ssh to be used for deployment

#### Returns

- `str` - public ssh key or empty string if not found

### OCPDeployment().test_cluster

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/ocp.py#L157)

```python
def test_cluster():
```

Test if OCP cluster installed successfuly
