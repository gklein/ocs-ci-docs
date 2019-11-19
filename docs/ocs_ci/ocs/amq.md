# AMQ

> Auto-generated documentation for [ocs_ci.ocs.amq](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py) module.

AMQ Class to run amq specific tests

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / AMQ
    - [AMQ](#amq)
        - [AMQ().cleanup](#amqcleanup)
        - [AMQ().is_amq_pod_running](#amqis_amq_pod_running)
        - [AMQ().setup_amq](#amqsetup_amq)
        - [AMQ().setup_amq_cluster_operator](#amqsetup_amq_cluster_operator)
        - [AMQ().setup_amq_kafka_bridge](#amqsetup_amq_kafka_bridge)
        - [AMQ().setup_amq_kafka_connect](#amqsetup_amq_kafka_connect)
        - [AMQ().setup_amq_kafka_persistent](#amqsetup_amq_kafka_persistent)

## AMQ

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py#L20)

```python
class AMQ(object):
    def __init__(**kwargs):
```

Workload operation using AMQ

### AMQ().cleanup

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py#L207)

```python
def cleanup():
```

Clean up function,
will start to delete from amq cluster operator
then amq-connector, persistent, bridge, at the end it will delete the created namespace

### AMQ().is_amq_pod_running

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py#L103)

```python
def is_amq_pod_running(pod_pattern='cluster-operator'):
```

The function checks if provided pod_pattern finds a pod and if the status is running or not

#### Arguments

- `pod_pattern` *str* - the pattern for pod

#### Returns

- `bool` - status of pod: True if found pod is running

### AMQ().setup_amq

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py#L195)

```python
def setup_amq():
```

Setup AMQ from local folder,
function will call all necessary sub functions to make sure amq installation is complete

### AMQ().setup_amq_cluster_operator

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py#L80)

```python
def setup_amq_cluster_operator():
```

Function to setup amq-cluster_operator,
the file file is pulling from github
it will make sure cluster-operator pod is running

### AMQ().setup_amq_kafka_bridge

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py#L175)

```python
def setup_amq_kafka_bridge():
```

Function to setup amq-kafka, the file file is pulling from github
it will make kind: KafkaBridge and will make sure the pod status is running

Return: kafka_bridge object

### AMQ().setup_amq_kafka_connect

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py#L155)

```python
def setup_amq_kafka_connect():
```

The function is to setup amq-kafka-connect, the yaml file is pulling from github
it will make kind: KafkaConnect and will make sure the status is running

Returns: kafka_connect object

### AMQ().setup_amq_kafka_persistent

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/amq.py#L134)

```python
def setup_amq_kafka_persistent():
```

Function to setup amq-kafka-persistent, the file file is pulling from github
it will make kind: Kafka and will make sure the status is running

#### Returns

kafka_persistent
