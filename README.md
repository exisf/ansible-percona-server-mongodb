Ansible percona server mongodb
=========

Ansible role to set up percona-server-mongodb.

Supports:
- Encyption at rest
- Admin user create
- Replication on multi instance

Tested on
-----------
Ubuntu 20 and 22, Disk: 250+, x86_64, 4GB of RAM

Role Variables
--------------
```
Varables for this role are in the defaults.yml
PM_apt_repository: 
PM_release_version:
PM_rs_port:
PM_packages:
PM_bind_IP: 
PM_data_dir: 
PM_admin_password: 
PM_encryption_key_file:
PM_keyfile:
```

Example Playbook
----------------
```
- hosts: all
  gather_facts: yes
  become: true
  
  roles:
    - { role: ansible_role_mongodb_percona, tags: percona }
```

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
Excel Felix