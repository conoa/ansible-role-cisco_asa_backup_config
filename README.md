cisco_asa_backup_config
=======================

A role that creates backups of configurations in a Cisco ASA.
The role works with ASAs both with and without security contexts.

Requirements
------------

This role requires the [asa command module](https://docs.ansible.com/ansible/latest/collections/cisco/asa/asa_command_module.html), which can be installed by `ansible-galaxy collection install cisco.asa`

Role Variables
--------------

#### backup_destination:
This option provides the path ending with directory name in which the backup configuration file(s) will be stored. If the directory does not exist it will be first created.
If the variable is not given a backup directory named `backup` will be created in the current working directory and backups will be copied to that directory.

Example Playbook
----------------

```
- hosts: all
  gather_facts: no
  roles:
    - cisco_asa_backup_config

  vars:
    backup_destination: /tmp/asa_backups/
```

Example host definition
-----------------------

```
[ciscoasa]
192.168.0.1

[ciscoasa:vars]
ansible_connection=ansible.netcommon.network_cli
ansible_network_os=cisco.asa.asa
ansible_user=cisco
ansible_password=cisco
ansible_become_password=cisco
```

License
-------

BSD

Author Information
------------------

Farid Joubbi - Conoa - https://conoa.se
