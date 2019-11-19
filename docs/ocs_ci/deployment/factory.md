# Factory

> Auto-generated documentation for [ocs_ci.deployment.factory](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/factory.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Deployment](index.md#deployment) / Factory
    - [DeploymentFactory](#deploymentfactory)
        - [DeploymentFactory().get_deployment](#deploymentfactoryget_deployment)

## DeploymentFactory

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/factory.py#L11)

```python
class DeploymentFactory(object):
    def __init__():
```

A factory class to get specific platform object

### DeploymentFactory().get_deployment

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/deployment/factory.py#L20)

```python
def get_deployment():
```

Get the exact deployment class based on ENV_DATA

#### Examples

deployment_platform may look like 'aws', 'vmware', 'baremetal'
deployment_type may be like 'ipi' or 'upi'
