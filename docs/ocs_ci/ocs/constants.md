# Constants

> Auto-generated documentation for [ocs_ci.ocs.constants](https://github.com/gklein/ocs-ci/blob/master/ocs_ci/ocs/constants.py) module.

Constants module.

- [Ocs-ci](../../README.md#ocs-ci) / [Modules](../../MODULES.md#ocs-ci-modules) / [Ocs Ci](../index.md#ocs-ci) / [Ocs](index.md#ocs) / Constants

This module contains any values that are widely used across the framework,
utilities, or tests that will predominantly remain unchanged.

In the event values here have to be changed it should be under careful review
and with consideration of the entire project.

#### Attributes

- `TOP_DIR` - Directories: `os.path.dirname(os.path.dirname(os.path.dirname(os.path.abspath(__file__))))`
- `STATUS_PENDING` - Statuses: `'Pending'`
- `CEPHFILESYSTEM` - Resources / Kinds: `'CephFileSystem'`
- `AWS_EFS_PROVISIONER` - Provisioners: `'openshift.org/aws-efs'`
- `SECRET` - Other: `'Secret'`
- `ADMIN_USER` - encoded value of 'admin': `'admin'`
- `RECLAIM_POLICY_RETAIN` - Reclaim Policy: `'Retain'`
- `ACCESS_MODE_RWO` - Access Mode: `'ReadWriteOnce'`
- `MON_APP_LABEL` - Pod label: `'app=rook-ceph-mon'`
- `TOOL_POD_YAML` - YAML paths: `os.path.join(TEMPLATE_DEPLOYMENT_DIR, 'toolbox_pod.yaml')`
- `EO_NAMESPACE_YAML` - Openshift-logging elasticsearch operator deployment yamls: `os.path.join(TEMPLATE_DEPLOYMENT_EO, 'eo-project.yaml')`
- `CL_NAMESPACE_YAML` - Openshift-logging clusterlogging operator deployment yamls: `os.path.join(TEMPLATE_DEPLOYMENT_CLO, 'cl-namespace.yaml')`
- `FIO_IO_PARAMS_YAML` - Workload-io yamls: `os.path.join(TEMPLATE_FIO_DIR, 'workload_io.yaml')`
- `RSYNC_POD_YAML` - Openshift infra yamls:: `os.path.join(TEMPLATE_OPENSHIFT_INFRA_DIR, 'rsync-pod.yaml')`
- `RBD_INTERFACE` - constants: `'rbd'`
- `INSTANCE_PENDING` - EC2 instance statuses: `0`
- `NODE_READY` - Node statuses: `'Ready'`
- `ALERT_CLUSTERERRORSTATE` - Alert labels: `'CephClusterErrorState'`
- `OPERATOR_NODE_LABEL` - OCS Deployment related constants: `"cluster.ocs.openshift.io/openshift-storage=''"`
- `AWS_PLATFORM` - Platforms: `'aws'`
- `DEFAULT_SC_AWS` - Default SC based on platforms: `'gp2'`
- `BOOTSTRAP_IGN` - ignition files: `'bootstrap.ign'`
- `VSPHERE_INSTALLER_REPO` - vSphere related constants: `'https://github.com/openshift/installer.git'`
- `config_keys_patterns_to_censor` - Config related constants: `['passw', 'token', 'secret']`
- `OCP4_2_REPO` - repos: `os.path.join(REPO_DIR, 'ocp_4_2.repo')`
- `RHEL_POD_PACKAGES` - packages: `['openssh-clients', 'openshift-ansible', 'openshift-clients', 'jq']`
- `ORDER_BEFORE_UPGRADE` - Upgrade related constants, keeping some space between, so we can add
  additional order.: `10`
- `OCS_CSV_PREFIX` - Deployment constants: `'ocs-operator'`
