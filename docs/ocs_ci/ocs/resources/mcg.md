# MCG

> Auto-generated documentation for [ocs_ci.ocs.resources.mcg](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py) module.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Ocs](../index.md#ocs) / [Resources](index.md#resources) / MCG
    - [MCG](#mcg)
        - [MCG().check_data_reduction](#mcgcheck_data_reduction)
        - [MCG().cli_list_all_bucket_names](#mcgcli_list_all_bucket_names)
        - [MCG().cli_verify_bucket_exists](#mcgcli_verify_bucket_exists)
        - [MCG().oc_list_all_bucket_names](#mcgoc_list_all_bucket_names)
        - [MCG().oc_verify_bucket_exists](#mcgoc_verify_bucket_exists)
        - [MCG().s3_get_all_buckets](#mcgs3_get_all_buckets)
        - [MCG().s3_list_all_bucket_names](#mcgs3_list_all_bucket_names)
        - [MCG().s3_list_all_objects_in_bucket](#mcgs3_list_all_objects_in_bucket)
        - [MCG().s3_verify_bucket_exists](#mcgs3_verify_bucket_exists)
        - [MCG().send_rpc_query](#mcgsend_rpc_query)
        - [MCG().verify_s3_object_integrity](#mcgverify_s3_object_integrity)

## MCG

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L19)

```python
class MCG(object):
    def __init__():
```

Wrapper class for the Multi Cloud Gateway's S3 service

### MCG().check_data_reduction

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L219)

```python
def check_data_reduction(bucketname):
```

Checks whether the data reduction on the MCG server works properly

#### Arguments

- `bucketname` - An example bucket name that contains compressed/deduped data

#### Returns

- `bool` - True if the data reduction mechanics work, False otherwise

### MCG().cli_list_all_bucket_names

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L102)

```python
def cli_list_all_bucket_names():
```

#### Returns

- `list` - A list of all bucket names

### MCG().cli_verify_bucket_exists

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L186)

```python
def cli_verify_bucket_exists(bucketname):
```

Verifies whether a bucket with the given bucketname exists

#### Arguments

bucketname : The bucket name to be verified

#### Returns

- `bool` - True if bucket exists, False otherwise

### MCG().oc_list_all_bucket_names

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L91)

```python
def oc_list_all_bucket_names():
```

#### Returns

- `list` - A list of all bucket names

### MCG().oc_verify_bucket_exists

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L166)

```python
def oc_verify_bucket_exists(bucketname):
```

Verifies whether a bucket with the given bucketname exists

#### Arguments

bucketname : The bucket name to be verified

#### Returns

- `bool` - True if bucket exists, False otherwise

### MCG().s3_get_all_buckets

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L118)

```python
def s3_get_all_buckets():
```

#### Returns

- `list` - A list of all s3.Bucket objects

### MCG().s3_list_all_bucket_names

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L83)

```python
def s3_list_all_bucket_names():
```

#### Returns

- `list` - A list of all bucket names

### MCG().s3_list_all_objects_in_bucket

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L111)

```python
def s3_list_all_objects_in_bucket(bucketname):
```

#### Returns

- `list` - A list of all bucket objects

### MCG().s3_verify_bucket_exists

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L126)

```python
def s3_verify_bucket_exists(bucketname):
```

Verifies whether a bucket with the given bucketname exists

#### Arguments

bucketname : The bucket name to be verified

#### Returns

- `bool` - True if bucket exists, False otherwise

### MCG().send_rpc_query

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L198)

```python
def send_rpc_query(api, method, params):
```

Templates and sends an RPC query to the MCG mgmt endpoint

#### Arguments

- `api` - The name of the API to use
- `method` - The method to use inside the API
- `params` - A dictionary containing the command payload

#### Returns

The server's response

### MCG().verify_s3_object_integrity

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/mcg.py#L144)

```python
def verify_s3_object_integrity(
    original_object_path,
    result_object_path,
    awscli_pod,
):
```

Verifies checksum between orignial object and result object on an awscli pod

#### Arguments

- `original_object_path` *str* - The Object that is uploaded to the s3 bucket
- `result_object_path` *str* - The Object that is downloaded from the s3 bucket
- `awscli_pod` *pod* - A pod running the AWSCLI tools

#### Returns

- `bool` - True if checksum matches, False otherwise
