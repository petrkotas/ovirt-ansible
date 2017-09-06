oVirt host deploy - libvirt-guests
=============================

This role is used for configuration of libvirt-guests on oVirt hypervisor.
To make the libvirt-guests play nicely with the VDSM, these options are set:
  - libvirt-guests service is started and enables
  - optionaly set shutdown timeout
  - optionaly enable parallel shutdown

Requirements
------------

 * Ansible version 2.0

Role Variables
--------------

| Name                          |  Description                                       |
|-------------------------------|----------------------------------------------------|
| host_deploy_shutdown_timeout  | Timeout before systemd starts killing processes    |
| host_deploy_shutdown_parallel | If set VMs are shutdown in parallel with count set |

Dependencies
------------

No.

Example Playbook
----------------

```yaml
- name: oVirt host deploy - libvirt-guests
  hosts: hostname

  vars:
    host_deploy_shutdown_timeout: 9001
    host_deploy_shutdown_parallel: 0

  roles:
    - ovirt-host-deploy-libvirt-guests
```

License
-------

Apache License 2.0
