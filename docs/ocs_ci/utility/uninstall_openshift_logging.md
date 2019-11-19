# Uninstall Openshift Logging

> Auto-generated documentation for [ocs_ci.utility.uninstall_openshift_logging](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/uninstall_openshift_logging.py) module.

Function to teardown the openshift-logging

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / Uninstall Openshift Logging
    - [check_pod_vanished](#check_pod_vanished)
    - [uninstall_cluster_logging](#uninstall_cluster_logging)

## check_pod_vanished

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/uninstall_openshift_logging.py#L14)

```python
@retry(UnexpectedBehaviour, 5, 30, 2)
def check_pod_vanished(pod_names):
```

A function to check all the pods are vanished from the namespace

## uninstall_cluster_logging

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/uninstall_openshift_logging.py#L26)

```python
def uninstall_cluster_logging():
```

Function to uninstall cluster-logging from the cluster
* Deletes the project "openshift-logging"
    and "openshift-operators-redhat"
