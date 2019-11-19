# Retry

> Auto-generated documentation for [ocs_ci.utility.retry](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/retry.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / Retry
    - [retry](#retry)

## retry

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/retry.py#L8)

```python
def retry(exception_to_check, tries=4, delay=3, backoff=2):
```

Retry calling the decorated function using exponential backoff.

#### Arguments

- `exception_to_check` - the exception to check. may be a tuple of exceptions to check
- `tries` - number of times to try (not retry) before giving up
- `delay` - initial delay between retries in seconds
- `backoff` - backoff multiplier e.g. value of 2 will double the delay each retry
