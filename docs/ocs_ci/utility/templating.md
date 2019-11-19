# Templating

> Auto-generated documentation for [ocs_ci.utility.templating](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / Templating
    - [Templating](#templating)
        - [Templating().base_path](#templatingbase_path)
        - [Templating().base_path](#templatingbase_path)
        - [Templating().render_template](#templatingrender_template)
    - [dump_data_to_json](#dump_data_to_json)
    - [dump_data_to_temp_yaml](#dump_data_to_temp_yaml)
    - [dump_to_temp_yaml](#dump_to_temp_yaml)
    - [generate_yaml_from_jinja2_template_with_data](#generate_yaml_from_jinja2_template_with_data)
    - [get_n_document_from_yaml](#get_n_document_from_yaml)
    - [load_config_data](#load_config_data)
    - [load_yaml](#load_yaml)
    - [to_nice_yaml](#to_nice_yaml)

## Templating

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L52)

```python
class Templating():
    def __init__(base_path=TEMPLATE_DIR):
```

Class which provides all functionality for templating

#### See also

- [TEMPLATE_DIR](../ocs/constants.md#template_dir)

### Templating().base_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L87)

```python
@property
def base_path():
```

Setter for self._base_path property

### Templating().base_path

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L94)

```python
@base_path.setter
def base_path(path):
```

Setter for self._base_path property

#### Arguments

- `path` *str* - Base path from which look for templates

### Templating().render_template

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L67)

```python
def render_template(template_path, data):
```

Render a template with the given data.

#### Arguments

- `template_path` *str* - location of the j2 template from the
    self._base_path
- `data` *dict* - the data to be formatted into the template

- `Returns` - rendered template

## dump_data_to_json

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L206)

```python
def dump_data_to_json(data, json_file):
```

Dump data to json file

#### Arguments

- `data` *dict* - dictionary with data to dump to the json file.
- `json_file` *str* - file path to json file

## dump_data_to_temp_yaml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L185)

```python
def dump_data_to_temp_yaml(data, temp_yaml):
```

Dump data to temporary yaml file

#### Arguments

data (dict or list): dict or list (in case of multi_document) with
    data to dump to the yaml file.
- `temp_yaml` *str* - file path of yaml file

#### Returns

- `str` - dumped yaml data

## dump_to_temp_yaml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L128)

```python
def dump_to_temp_yaml(src_file, dst_file, **kwargs):
```

Dump a jinja2 template file content into a yaml file
 Args:
    src_file (str): Template Yaml file path
    dst_file: the path to the destination Yaml file

## generate_yaml_from_jinja2_template_with_data

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L105)

```python
def generate_yaml_from_jinja2_template_with_data(file_, **kwargs):
```

Generate yaml fron jinja2 yaml with processed data

#### Arguments

- `file_` *str* - Template Yaml file path

All jinja2 attributes

#### Returns

- `dict` - Generated from template file

#### Examples

generate_yaml_from_template(file_='path/to/file/name', pv_data_dict')

## get_n_document_from_yaml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L163)

```python
def get_n_document_from_yaml(yaml_generator, index=0):
```

Returns n document from yaml generator loaded by load_yaml with
multi_document = True.

#### Arguments

- `yaml_generator` *generator* - Generator from yaml.safe_load_all
- `index` *int* - Index of document to return. (0 - 1st, 1 - 2nd document)

#### Returns

- `dict` - Data from n document from yaml file.

#### Raises

- `IndexError` - In case that yaml generator doesn't have such index.

## load_config_data

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L12)

```python
def load_config_data(data_path):
```

Loads YAML data from the specified path

#### Arguments

- `data_path` - location of the YAML data file

- `Returns` - loaded YAML data

## load_yaml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L140)

```python
def load_yaml(file, multi_document=False):
```

Load yaml file (local or from URL) and convert it to dictionary

#### Arguments

- `file` *str* - Path to the file or URL address
- `multi_document` *bool* - True if yaml contains more documents

#### Returns

- `dict` - If multi_document == False, returns loaded data from yaml file
    with one document.
- `generator` - If multi_document == True, returns generator which each
    iteration returns dict from one loaded document from a file.

## to_nice_yaml

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/templating.py#L26)

```python
def to_nice_yaml(a, indent=2, *args, **kw):
```

This is a j2 filter which allows you from dictionary to print nice human
readable yaml.

#### Arguments

- `a` *dict* - dictionary with data to print as yaml
- `indent` *int* - number of spaces for indent to be applied for whole
    dumped yaml. First line is not indented! (default: 2)
- `*args` - Other positional arguments which will be passed to yaml.dump
- `*args` - Other keywords arguments which will be passed to yaml.dump

#### Returns

- `str` - transformed yaml data in string format
