# PackageManifest

> Auto-generated documentation for [ocs_ci.ocs.resources.packagemanifest](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/packagemanifest.py) module.

Package manifest related functionalities

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Ocs](../index.md#ocs) / [Resources](index.md#resources) / PackageManifest
    - [PackageManifest](#packagemanifest)
        - [PackageManifest().get_channels](#packagemanifestget_channels)
        - [PackageManifest().get_current_csv](#packagemanifestget_current_csv)
        - [PackageManifest().get_default_channel](#packagemanifestget_default_channel)
        - [PackageManifest().wait_for_resource](#packagemanifestwait_for_resource)

## PackageManifest

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/packagemanifest.py#L13)

```python
class PackageManifest(OCP):
    def __init__(
        resource_name='',
        namespace=defaults.MARKETPLACE_NAMESPACE,
        **kwargs,
    ):
```

This class represent PackageManifest and contains all related methods.

#### See also

- [OCP](../ocp.md#ocp)

### PackageManifest().get_channels

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/packagemanifest.py#L50)

```python
def get_channels():
```

Returns channels for package manifest

#### Returns

- `list` - available channels for package manifest

#### Raises

- `ResourceNameNotSpecifiedException` - in case the name is not
    specified.

### PackageManifest().get_current_csv

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/packagemanifest.py#L65)

```python
def get_current_csv(channel=None):
```

Returns current csv for default or specified channel

#### Returns

- `str` - Current CSV name

#### Raises

- `ResourceNameNotSpecifiedException` - in case the name is not
    specified.

### PackageManifest().get_default_channel

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/packagemanifest.py#L35)

```python
def get_default_channel():
```

Returns default channel for package manifest

#### Returns

- `str` - default channel name

#### Raises

- `ResourceNameNotSpecifiedException` - in case the name is not
    specified.

### PackageManifest().wait_for_resource

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/packagemanifest.py#L83)

```python
def wait_for_resource(resource_name='', timeout=60, sleep=3):
```

Wait for a packagemanifest exists.

#### Arguments

- `resource_name` *str* - The name of the resource to wait for.
    If not specified the self.resource_name will be used. At least
    on of those has to be set!
- `timeout` *int* - Time in seconds to wait
- `sleep` *int* - Sampling time in seconds

#### Raises

- `ResourceNameNotSpecifiedException` - in case the name is not
    specified.
- `TimeoutExpiredError` - in case the resource not found in timeout
