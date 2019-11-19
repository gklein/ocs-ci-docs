# Framework

> Auto-generated documentation for [ocs_ci.framework](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/__init__.py) module.

Avoid already-imported warning cause of we are importing this package from
run wrapper for loading config.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / Framework
    - [Config](#config)
        - [Config().get_defaults](#configget_defaults)
        - [Config().reset](#configreset)
        - [Config().to_dict](#configto_dict)
        - [Config().update](#configupdate)
    - [merge_dict](#merge_dict)
    - Modules
        - [Exceptions](exceptions.md#exceptions)
        - [Main](main.md#main)
        - [pytest customization](pytest_customization/index.md#pytest-customization)
        - [Testlib](testlib.md#testlib)
        - [Tests](tests/index.md#tests)

You can see documentation here:
https://docs.pytest.org/en/latest/reference.html
under section PYTEST_DONT_REWRITE

## Config

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/__init__.py#L20)

```python
dataclass
class Config():
```

### Config().get_defaults

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/__init__.py#L38)

```python
def get_defaults():
```

Return a fresh copy of the default configuration

### Config().reset

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/__init__.py#L30)

```python
def reset():
```

Clear all configuration data and load defaults

### Config().to_dict

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/__init__.py#L61)

```python
def to_dict():
```

### Config().update

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/__init__.py#L45)

```python
def update(user_dict: dict):
```

Override configuration items with items in user_dict, without wiping
out non-overridden items

## merge_dict

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/__init__.py#L71)

```python
def merge_dict(orig: dict, new: dict) -> dict:
```

Update a dict recursively, with values from 'new' being merged into 'orig'.

#### Arguments

- `orig` *dict* - The object that will receive the update
- `new` *dict* - The object which is the source of the update

#### Examples

orig = {
    - `'dict'` - {'one': 1, 'two': 2},
    - `'list'` - [1, 2],
    - `'string'` - 's',
}
new = {
    - `'dict'` - {'one': 'one', 'three': 3},
    - `'list'` - [0],
    - `'string'` - 'x',
}
merge_dict(orig, new) ->
{
    - `'dict'` - {'one': 'one', 'two': 2, 'three': 3}
    - `'list'` - [0],
    'string', 'x',
}
