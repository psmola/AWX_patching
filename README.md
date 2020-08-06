# awx_patching
Ansible role responsible for upgrade AWX RPM  from version 9.2 to 11 

##Prerequisites 
AWX RPM repository configured (https://rpm.miracle.dk/AWX-RPM/CentOS_7/). 
New version AWX available for yum.

## Important
This role does not contain nginx configuration. Please be aware that in version 11
all static files are in different location
v9.2: /opt/awx/static/
v11: /var/lib/awx/public/static

and nginx configuration file  should be changed 

## Example playbook
```
---
 
- hosts: localhost
  become: yes
  become_method: sudo
  vars:
    awx_ansible_version: v11
  roles:
      - awx-patching
```
