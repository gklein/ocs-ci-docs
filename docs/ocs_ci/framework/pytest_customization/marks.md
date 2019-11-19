# Marks

> Auto-generated documentation for [ocs_ci.framework.pytest_customization.marks](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/framework/pytest_customization/marks.py) module.

In this pytest plugin we will keep all our pytest marks used in our tests and
all related hooks/plugins to markers.

- [Ocs-ci](../../../README.md#ocs-ci) / [Modules](../../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../../index.md#ocs-ci) / [Framework](../index.md#framework) / [pytest customization](index.md#pytest-customization) / Marks

#### Attributes

- `acceptance` - build acceptance: `pytest.mark.acceptance`
- `ocp` - components  and other markers: `pytest.mark.ocp`
- `order_pre_upgrade` - upgrade related markers
  Requires pytest ordering plugin installed: `pytest.mark.run(order=ORDER_BEFORE_UPGRADE)`
- `ignore_leftovers` - mark the test class with marker below to ignore leftover check: `pytest.mark.ignore_leftovers`
- `run_this` - testing marker this is just for testing purpose if you want to run some test
  under development, you can mark it with @run_this and run pytest -m run_this: `pytest.mark.run_this`
- `google_api_required` - Skipif marks: `pytest.mark.skipif(not os.path.exists(os.path.e...`
- `filter_insecure_request_warning` - Filter warnings: `pytest.mark.filterwarnings('ignore::urllib3.exc...`
