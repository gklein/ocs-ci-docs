# Prometheus

> Auto-generated documentation for [ocs_ci.utility.prometheus](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/prometheus.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / Prometheus
    - [PrometheusAPI](#prometheusapi)
        - [PrometheusAPI().check_alert_cleared](#prometheusapicheck_alert_cleared)
        - [PrometheusAPI().generate_cert](#prometheusapigenerate_cert)
        - [PrometheusAPI().get](#prometheusapiget)
        - [PrometheusAPI().refresh_connection](#prometheusapirefresh_connection)
        - [PrometheusAPI().wait_for_alert](#prometheusapiwait_for_alert)
    - [check_alert_list](#check_alert_list)

## PrometheusAPI

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/prometheus.py#L78)

```python
class PrometheusAPI(object):
    def __init__(user=None, password=None):
```

This is wrapper class for Prometheus API.

### PrometheusAPI().check_alert_cleared

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/prometheus.py#L233)

```python
def check_alert_cleared(label, measure_end_time, time_min=30):
```

Check that all alerts with provided label are cleared.

#### Arguments

- `label` *str* - Alerts label
- `measure_end_time` *int* - Timestamp of measurement end
- `time_min` *int* - Number of seconds to wait for alert to be cleared
    since measurement end

### PrometheusAPI().generate_cert

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/prometheus.py#L123)

```python
def generate_cert():
```

Generate CA certificate from kubeconfig for API.

TODO: find proper way how to generate/load cert files.

### PrometheusAPI().get

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/prometheus.py#L145)

```python
def get(resource, payload=None):
```

Get alerts from Prometheus API.

#### Arguments

- `resource` *str* - Represents part of uri that specifies given
    resource
- `payload` *dict* - Provide parameters to GET API call.
    e.g. for `alerts` resource this can be
    - `{'silenced'` - False, 'inhibited': False}

#### Returns

- `dict` - Response from Prometheus alerts api

### PrometheusAPI().refresh_connection

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/prometheus.py#L108)

```python
def refresh_connection():
```

Login into OCP, refresh endpoint and token.

### PrometheusAPI().wait_for_alert

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/prometheus.py#L175)

```python
def wait_for_alert(name, state=None, timeout=1200, sleep=5):
```

Search for alerts that have requested name and state.

#### Arguments

- `name` *str* - Alert name
- `state` *str* - Alert state, if provided then there are searched
    alerts with provided state. If not provided then alerts are
    searched for absence of the alert. Loop that looks for alerts
    is broken when there are no alerts returned from API. This
    is done because API is not returning any alerts that are not
    in pending or firing state
- `timeout` *int* - Number of seconds for how long the alert should
    be searched
- `sleep` *int* - Number of seconds to sleep in between alert search

#### Returns

- `list` - List of alert records

## check_alert_list

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/prometheus.py#L16)

```python
def check_alert_list(
    label,
    msg,
    alerts,
    states,
    severity='warning',
    ignore_more_occurences=False,
):
```

Check list of alerts that there are alerts with requested label and
message for each provided state. If some alert is missing then this check
fails.

#### Arguments

- `label` *str* - Alert label
- `msg` *str* - Alert message
- `alerts` *list* - List of alerts to check
- `states` *list* - List of states to check, order is important
- `ignore_more_occurences` *bool* - If true then there is checkced only
    occurence of alert with requested label, message and state but
    it is not checked if there is more of occurences than one.
