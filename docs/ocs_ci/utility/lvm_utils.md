# Lvm Utils

> Auto-generated documentation for [ocs_ci.utility.lvm_utils](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py) module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Utility](index.md#utility) / Lvm Utils
    - [lvcreate](#lvcreate)
    - [make_partition](#make_partition)
    - [osd_scenario1](#osd_scenario1)
    - [osd_scenario1_dmcrypt](#osd_scenario1_dmcrypt)
    - [osd_scenario2](#osd_scenario2)
    - [osd_scenario2_dmcrypt](#osd_scenario2_dmcrypt)
    - [osd_scenario3](#osd_scenario3)
    - [osd_scenario3_dmcrypt](#osd_scenario3_dmcrypt)
    - [pvcreate](#pvcreate)
    - [vgcreate](#vgcreate)

## lvcreate

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L10)

```python
def lvcreate(osd, lv_name, vg_name, size):
```

## make_partition

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L15)

```python
def make_partition(osd, device, start=None, end=None, gpt=False):
```

## osd_scenario1

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L20)

```python
def osd_scenario1(osd, devices_dict, dmcrypt=False):
```

OSD scenario type1 generator

#### Arguments

- `osd` - osd node
- `devices_dict` - dict of devices of the osd node supplied
- `dmcrypt` - False by default

#### Returns

generated scenario, dmcrypt

## osd_scenario1_dmcrypt

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L95)

```python
def osd_scenario1_dmcrypt(osd, devices_dict):
```

OSD scenario type2 generator

#### Arguments

- `osd` - osd node
- `devices_dict` - dict of devices of the osd node supplied
- `dmcrypt` - False by default

#### Returns

generated scenario, dmcrypt(overridden to True)

## osd_scenario2

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L110)

```python
def osd_scenario2(osd, devices_dict, dmcrypt=False):
```

OSD scenario type3 generator

#### Arguments

- `osd` - osd node
- `devices_dict` - dict of devices of the osd node supplied
- `dmcrypt` - False by default

#### Returns

generated scenario, dmcrypt

## osd_scenario2_dmcrypt

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L137)

```python
def osd_scenario2_dmcrypt(osd, devices_dict):
```

OSD scenario type4 generator

#### Arguments

- `osd` - osd node
- `devices_dict` - dict of devices of the osd node supplied
- `dmcrypt` - False by default

#### Returns

generated scenario, dmcrypt(overridden to True)

## osd_scenario3

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L152)

```python
def osd_scenario3(osd, devices_dict, dmcrypt=False):
```

OSD scenario type5 generator

#### Arguments

- `osd` - osd node
- `devices_dict` - dict of devices of the osd node supplied
- `dmcrypt` - False by default

#### Returns

generated scenario, dmcrypt

## osd_scenario3_dmcrypt

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L197)

```python
def osd_scenario3_dmcrypt(osd, devices_dict):
```

OSD scenario type6 generator

#### Arguments

- `osd` - osd node
- `devices_dict` - dict of devices of the osd node supplied
- `dmcrypt` - False by default

#### Returns

generated scenario, dmcrypt(overridden to True)

## pvcreate

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L1)

```python
def pvcreate(osd, devices):
```

## vgcreate

[[find in source code]](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/utility/lvm_utils.py#L5)

```python
def vgcreate(osd, vg_name, devices):
```
