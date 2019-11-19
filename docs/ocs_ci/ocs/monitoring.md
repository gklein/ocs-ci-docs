# Monitoring

> Auto-generated documentation for [ocs_ci.ocs.monitoring](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/monitoring.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Monitoring
    - [check_ceph_health_status_metrics_on_prometheus](#check_ceph_health_status_metrics_on_prometheus)
    - [check_pvcdata_collected_on_prometheus](#check_pvcdata_collected_on_prometheus)
    - [create_configmap_cluster_monitoring_pod](#create_configmap_cluster_monitoring_pod)
    - [get_list_pvc_objs_created_on_monitoring_pods](#get_list_pvc_objs_created_on_monitoring_pods)
    - [get_metrics_persistentvolumeclaims_info](#get_metrics_persistentvolumeclaims_info)
    - [validate_pvc_are_mounted_on_monitoring_pods](#validate_pvc_are_mounted_on_monitoring_pods)
    - [validate_pvc_created_and_bound_on_monitoring_pods](#validate_pvc_created_and_bound_on_monitoring_pods)

## check_ceph_health_status_metrics_on_prometheus

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/monitoring.py#L138)

```python
def check_ceph_health_status_metrics_on_prometheus(mgr_pod):
```

Check ceph health status metric is collected on prometheus pod

#### Arguments

- `mgr_pod` *str* - Name of the mgr pod

#### Returns

- `bool` - True on success, false otherwise

## check_pvcdata_collected_on_prometheus

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/monitoring.py#L112)

```python
@retry(UnexpectedBehaviour, tries=10, delay=3, backoff=1)
def check_pvcdata_collected_on_prometheus(pvc_name):
```

Checks whether initially pvc related data is collected on pod

#### Arguments

- `pvc_name` *str* - Name of the pvc

#### Returns

True on success, raises UnexpectedBehaviour on failures

## create_configmap_cluster_monitoring_pod

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/monitoring.py#L18)

```python
def create_configmap_cluster_monitoring_pod(sc_name):
```

Create a configmap named cluster-monitoring-config
and configure pvc on monitoring pod

#### Arguments

- `sc_name` *str* - Name of the storage class

## get_list_pvc_objs_created_on_monitoring_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/monitoring.py#L77)

```python
def get_list_pvc_objs_created_on_monitoring_pods():
```

Returns list of pvc objects created on monitoring pods

#### Returns

- `list` - List of pvc objs

## get_metrics_persistentvolumeclaims_info

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/monitoring.py#L97)

```python
def get_metrics_persistentvolumeclaims_info():
```

Returns the created pvc information on prometheus pod

#### Returns

- `response.content` *dict* - The pvc metrics collected on prometheus pod

## validate_pvc_are_mounted_on_monitoring_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/monitoring.py#L60)

```python
def validate_pvc_are_mounted_on_monitoring_pods(pod_list):
```

Validate created pvc are mounted on monitoring pods

#### Arguments

- `pod_list` *list* - List of the pods where pvc are mounted

## validate_pvc_created_and_bound_on_monitoring_pods

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/monitoring.py#L42)

```python
def validate_pvc_created_and_bound_on_monitoring_pods():
```

Validate pvc's created and bound in state
on monitoring pods
