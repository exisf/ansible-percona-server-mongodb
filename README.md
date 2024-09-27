Role Name
=========

Ansible role to set up percona-server-mongodb.

Supports:
- Encyption at rest
- Admin user create
- Replication on multi instance

Tested
-----------
Ubuntu 20, 22

Requirements
------------

x86_64
min 4GB of RAM
Disk: 250+

Role Variables
--------------
Varables for this role are in the defaults.uml
PM_apt_repository: 
PM_release_version:
PM_rs_port:
PM_packages:
PM_bind_IP: 
PM_data_dir: 
PM_admin_password: 
PM_encryption_key_file:
PM_keyfile:

Dependencies
------------
- Ensure  percona-server-mongodb server installation requirement is setup 

Example Playbook
----------------
- hosts: all
  gather_facts: yes
  become: true

  
  roles:
    - { role: ansible_role_mongodb_percona, tags: percona }

inventory
----------------
```
all:
  hosts:
  children:
    mongodb_master:
      hosts:
        remote1:
          ansible_host: 
    mongodb_slave:
      hosts:
        remote4:
          ansible_host: 
        remote5:
          ansible_host: 
```


Author Information
------------------
ExcelFelix