# Exceptions

> Auto-generated documentation for [ocs_ci.ocs.exceptions](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Exceptions
    - [CephHealthException](#cephhealthexception)
    - [ClassCreationException](#classcreationexception)
    - [CommandFailed](#commandfailed)
    - [DeploymentPlatformNotSupported](#deploymentplatformnotsupported)
    - [MDSCountException](#mdscountexception)
    - [MissingRequiredConfigKeyError](#missingrequiredconfigkeyerror)
    - [MonCountException](#moncountexception)
    - [NotSupportedFunctionError](#notsupportedfunctionerror)
    - [PerformanceException](#performanceexception)
    - [ResourceInUnexpectedState](#resourceinunexpectedstate)
    - [ResourceLeftoversException](#resourceleftoversexception)
    - [ResourceNameNotSpecifiedException](#resourcenamenotspecifiedexception)
    - [ResourceWrongStatusException](#resourcewrongstatusexception)
    - [SameNamePrefixClusterAlreadyExistsException](#samenameprefixclusteralreadyexistsexception)
    - [TagNotFoundException](#tagnotfoundexception)
    - [TimeoutException](#timeoutexception)
    - [TimeoutExpiredError](#timeoutexpirederror)
    - [UnavailableBuildException](#unavailablebuildexception)
    - [UnavailableResourceException](#unavailableresourceexception)
    - [UnexpectedBehaviour](#unexpectedbehaviour)
    - [UnsupportedOSType](#unsupportedostype)
    - [VMMaxDisksReachedException](#vmmaxdisksreachedexception)

## CephHealthException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L9)

```python
class CephHealthException(Exception):
```

## ClassCreationException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L17)

```python
class ClassCreationException(Exception):
```

## CommandFailed

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L1)

```python
class CommandFailed(Exception):
```

## DeploymentPlatformNotSupported

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L47)

```python
class DeploymentPlatformNotSupported(Exception):
```

## MDSCountException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L43)

```python
class MDSCountException(Exception):
```

## MissingRequiredConfigKeyError

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L93)

```python
class MissingRequiredConfigKeyError(Exception):
```

## MonCountException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L39)

```python
class MonCountException(Exception):
```

## NotSupportedFunctionError

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L97)

```python
class NotSupportedFunctionError(Exception):
```

## PerformanceException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L55)

```python
class PerformanceException(Exception):
```

## ResourceInUnexpectedState

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L81)

```python
class ResourceInUnexpectedState(Exception):
```

## ResourceLeftoversException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L21)

```python
class ResourceLeftoversException(Exception):
```

## ResourceNameNotSpecifiedException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L77)

```python
class ResourceNameNotSpecifiedException(Exception):
```

## ResourceWrongStatusException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L59)

```python
class ResourceWrongStatusException(Exception):
    def __init__(resource_name, describe_out):
```

## SameNamePrefixClusterAlreadyExistsException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L89)

```python
class SameNamePrefixClusterAlreadyExistsException(Exception):
```

## TagNotFoundException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L73)

```python
class TagNotFoundException(Exception):
```

## TimeoutException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L35)

```python
class TimeoutException(Exception):
```

## TimeoutExpiredError

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L25)

```python
class TimeoutExpiredError(Exception):
    def __init__(*value):
```

## UnavailableBuildException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L51)

```python
class UnavailableBuildException(Exception):
```

## UnavailableResourceException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L69)

```python
class UnavailableResourceException(Exception):
```

## UnexpectedBehaviour

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L13)

```python
class UnexpectedBehaviour(Exception):
```

## UnsupportedOSType

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L5)

```python
class UnsupportedOSType(Exception):
```

## VMMaxDisksReachedException

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/exceptions.py#L85)

```python
class VMMaxDisksReachedException(Exception):
```
