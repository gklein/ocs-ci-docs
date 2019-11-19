# parallel

> Auto-generated documentation for [ocs_ci.ocs.parallel](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/parallel.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / parallel
    - [ExceptionHolder](#exceptionholder)
    - [parallel](#parallel)
        - [parallel().spawn](#parallelspawn)
    - [capture_traceback](#capture_traceback)
    - [resurrect_traceback](#resurrect_traceback)

## ExceptionHolder

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/parallel.py#L10)

```python
class ExceptionHolder(object):
    def __init__(exc_info):
```

## parallel

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/parallel.py#L37)

```python
class parallel(object):
    def __init__():
```

This class is a context manager for running functions in parallel.

You add functions to be run with the spawn method

```python
with parallel() as p:
    for foo in bar:
        p.spawn(quux, foo, baz=True)
```

You can iterate over the results (which are in arbitrary order)

```python
with parallel() as p:
    for foo in bar:
        p.spawn(quux, foo, baz=True)
    for result in p:
        print result
```

If one of the spawned functions throws an exception, it will be thrown
when iterating over the results, or when the with block ends.

At the end of the with block, the main thread waits until all
spawned functions have completed, or, if one exited with an exception,
kills the rest and raises the exception.

### parallel().spawn

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/parallel.py#L70)

```python
def spawn(func, *args, **kwargs):
```

## capture_traceback

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/parallel.py#L15)

```python
def capture_traceback(func, *args, **kwargs):
```

Utility function to capture tracebacks of any exception func
raises.

## resurrect_traceback

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/parallel.py#L26)

```python
def resurrect_traceback(exc):
```
