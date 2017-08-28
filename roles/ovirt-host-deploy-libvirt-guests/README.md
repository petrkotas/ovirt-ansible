oVirt host deploy - libvirt-guests
=============================

This role is used for configuration of libvirt-guests on oVirt hypervisor.
To make the libvirt-guests play nicely with the VDSM, these options are set:
 - the on-boot event is disabled
 - the on-shutdown event is set to shutdown, instead of hibernate
 - the default timeout is risen to 600 seconds and can be configured

Requirements
------------

 * Ansible version 2.0

Role Variables
--------------

| Name                          | Default value  | Description                                                       |
|-------------------------------|----------------|-------------------------------------------------------------------|
| host_deploy_cluster_version   | 4.2            | The version of the cluster where the host resides. Based on this version the role will enable cluster version specific firewalld rules. |
| host_deploy_shutdown_timeout  | 600            | Timeout before systemd starts killing processes     |
| host_deploy_shutdown_parallel | 0              | If set VMs are shutdown in parallel with count set |

Dependencies
------------

No.

Example Playbook
----------------

```yaml
- name: oVirt host deploy - firewalld
  hosts: hostname

  vars:
    host_deploy_cluster_version: 4.2
    host_deploy_shutdown_timeout: 9001
    host_deploy_shutdown_parallel: 0

  roles:
    - ovirt-host-deploy-firewalld
```

License
-------

Apache License 2.0
