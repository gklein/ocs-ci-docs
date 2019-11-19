# CatalogSource

> Auto-generated documentation for [ocs_ci.ocs.resources.catalog_source](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/catalog_source.py) module.

CatalogSource related functionalities

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Ocs](../index.md#ocs) / [Resources](index.md#resources) / CatalogSource
    - [CatalogSource](#catalogsource)
        - [CatalogSource().check_state](#catalogsourcecheck_state)
        - [CatalogSource().get_image_name](#catalogsourceget_image_name)
        - [CatalogSource().get_image_url](#catalogsourceget_image_url)
        - [CatalogSource().wait_for_state](#catalogsourcewait_for_state)

## CatalogSource

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/catalog_source.py#L15)

```python
class CatalogSource(OCP):
    def __init__(resource_name='', namespace=None, *args, **kwargs):
```

This class represent CatalogSource and contains all related
methods we need to do with it.

#### See also

- [OCP](../ocp.md#ocp)

### CatalogSource().check_state

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/catalog_source.py#L74)

```python
def check_state(state):
```

Check state of catalog source

#### Arguments

- `state` *str* - State of CatalogSource object

#### Returns

- `bool` - True if state of object is the same as desired one, False
    otherwise.

### CatalogSource().get_image_name

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/catalog_source.py#L37)

```python
def get_image_name():
```

Fetch image name from catalog source resource

#### Returns

image info (str): especially version info extracted from image
    name

### CatalogSource().get_image_url

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/catalog_source.py#L56)

```python
def get_image_url():
```

Fetch image url from catalog source resource

#### Returns

image url (str): URL of image

### CatalogSource().wait_for_state

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/resources/catalog_source.py#L110)

```python
@retry(ResourceInUnexpectedState, tries=4, delay=5, backoff=1)
def wait_for_state(state, timeout=480, sleep=5):
```

Wait till state of catalog source resource is the same as required one
passed in the state parameter.

#### Arguments

- `state` *str* - Desired state of catalog source object
- `timeout` *int* - Timeout in seconds to wait for desired state
- `sleep` *int* - Time in seconds to sleep between attempts

#### Raises

- `ResourceInUnexpectedState` - In case the catalog source is not in
    expected state.
