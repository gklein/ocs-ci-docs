# Deployment Openshift Logging

> Auto-generated documentation for [ocs_ci.utility.deployment_openshift_logging](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py) module.

This module deploys the openshift-logging on the cluster
EFK stack

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / Deployment Openshift Logging
    - [check_health_of_clusterlogging](#check_health_of_clusterlogging)
    - [create_clusterlogging_operator_group](#create_clusterlogging_operator_group)
    - [create_clusterlogging_subscription](#create_clusterlogging_subscription)
    - [create_elasticsearch_operator_group](#create_elasticsearch_operator_group)
    - [create_elasticsearch_subscription](#create_elasticsearch_subscription)
    - [create_instance_in_clusterlogging](#create_instance_in_clusterlogging)
    - [create_namespace](#create_namespace)
    - [set_rbac](#set_rbac)

## check_health_of_clusterlogging

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py#L263)

```python
@retry((CommandFailed, UnexpectedBehaviour), 10, 60, 2)
def check_health_of_clusterlogging():
```

* Checks for ElasticSearch, curator, fluentd and kibana pods in
openshift-logging namespace

* And check for the health of cluster logging, If status is green then the
cluster is healthy,if status is red then health is bad

#### Returns

- `list` - Gives all the pods that are present in the namespace

## create_clusterlogging_operator_group

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py#L145)

```python
def create_clusterlogging_operator_group(yaml_file):
```

Creation of operator-group for clusterlogging
operator.

#### Arguments

- `yaml_file` *str* - Path to yaml file to create operator group for
    cluster-logging operator
- `resource_name` *str* - Name of the operator group to create for
    cluster-logging operator

#### Returns

- `bool` - True if operator group for cluster-logging is created
    successfully, false otherwise

#### Examples

create_clusterlogging_operator_group(yaml_file=constants.CL_OG_YAML)

## create_clusterlogging_subscription

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py#L179)

```python
def create_clusterlogging_subscription(yaml_file):
```

Creation of subscription for clusterlogging to subscribe
a namespace to an operator

#### Arguments

- `yaml_file` *str* - Path to yaml file to create subscription for
    the namespace
- `resource_name` *str* - Name of the subscription

#### Returns

- `dict` - Contains all the details of the subscription.

#### Examples

cl_create_subscription(yaml_file=constants.CL_SUB_YAML)

## create_elasticsearch_operator_group

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py#L40)

```python
def create_elasticsearch_operator_group(yaml_file, resource_name):
```

Creation of operator-group for Elastic-search operator

#### Arguments

- `yaml_file` *str* - Path to yaml file to create operator group for
    elastic-search
- `resource_name` *str* - Name of the operator group to create for
    elastic-search

#### Returns

- `bool` - True if operator group for elastic search is created
    successfully, false otherwise

#### Examples

create_elasticsearch_operator_group(
    constants.EO_OG_YAML, 'openshift-operators-redhat'
)

## create_elasticsearch_subscription

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py#L113)

```python
def create_elasticsearch_subscription(yaml_file):
```

Creation of Subscription for the namespace
to subscribe a Namespace to an Operator.

#### Arguments

- `yaml_file` *str* - Path to yaml file to create subscription for
    a namespace
- `resource_name` *str* - Name of the subscription

#### Returns

- `dict` - Contains all the details of the subscription

#### Examples

create_elasticsearch_subscription(constants.EO_SUB_YAML)

## create_instance_in_clusterlogging

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py#L214)

```python
def create_instance_in_clusterlogging(sc_name=None):
```

Creation of instance for clusterlogging that creates PVCs,
ElasticSearch, curator fluentd and kibana pods and checks for all
the pods and PVCs

#### Arguments

- `sc_name` *str* - Storage class name to create PVCs

#### Returns

- `dict` - Contains all detailed information of the
    instance such as pods that got created, its resources and limits
    values, storage class and size details etc.

## create_namespace

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py#L19)

```python
def create_namespace(yaml_file):
```

Creation of namespace "openshift-operators-redhat"
for Elasticsearch-operator and "openshift-logging"
for ClusterLogging-operator

#### Arguments

- `yaml_file` *str* - Path to yaml file to create namespace

#### Examples

create_namespace(yaml_file=constants.EO_NAMESPACE_YAML)

## set_rbac

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/deployment_openshift_logging.py#L75)

```python
def set_rbac(yaml_file, resource_name):
```

Setting Role Based Access Control to grant Prometheus
permission to access the openshift-operators-redhat namespace

#### Arguments

- `yaml_file` *str* - Path to yaml file to create RBAC
    (ROLE BASED ACCESS CONTROL)
- `resource_name` *str* - Name of the resource for which we give RBAC
    permissions

#### Returns

- `bool` - True if RBAC is set successfully,
    false otherwise

#### Examples

set_rbac(constants.EO_RBAC_YAML, 'prometheus-k8s')
