# MCGBucket

> Auto-generated documentation for [ocs_ci.ocs.resources.mcg_bucket](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py) module.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Ocs](../index.md#ocs) / [Resources](index.md#resources) / MCGBucket
    - [CLIBucket](#clibucket)
        - [CLIBucket().internal_delete](#clibucketinternal_delete)
    - [MCGBucket](#mcgbucket)
        - [MCGBucket().delete](#mcgbucketdelete)
        - [MCGBucket().internal_delete](#mcgbucketinternal_delete)
    - [OCBucket](#ocbucket)
        - [OCBucket().internal_delete](#ocbucketinternal_delete)
    - [S3Bucket](#s3bucket)
        - [S3Bucket().internal_delete](#s3bucketinternal_delete)

## CLIBucket

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L86)

```python
class CLIBucket(MCGBucket):
    def __init__(*args, **kwargs):
```

Implementation of an MCG bucket using the NooBaa CLI

#### See also

- [MCGBucket](#mcgbucket)

### CLIBucket().internal_delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L94)

```python
def internal_delete():
```

Deletes the bucket using the NooBaa CLI

## MCGBucket

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L13)

```python
class MCGBucket(ABC):
    def __init__(mcg, name):
```

Base abstract class for MCG buckets

### MCGBucket().delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L36)

```python
def delete():
```

Super method that first logs the bucket deletion and then calls
the appropriate implementation

### MCGBucket().internal_delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L44)

```python
@abstractmethod
def internal_delete():
```

## OCBucket

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L65)

```python
class OCBucket(MCGBucket):
    def __init__(*args, **kwargs):
```

Implementation of an MCG bucket using the OC CLI

#### See also

- [MCGBucket](#mcgbucket)

### OCBucket().internal_delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L79)

```python
def internal_delete():
```

Deletes the bucket using the OC CLI

## S3Bucket

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L49)

```python
class S3Bucket(MCGBucket):
    def __init__(*args, **kwargs):
```

Implementation of an MCG bucket using the S3 API

#### See also

- [MCGBucket](#mcgbucket)

### S3Bucket().internal_delete

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg_bucket.py#L57)

```python
def internal_delete():
```

Deletes the bucket using the S3 API
