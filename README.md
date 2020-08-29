Role Name
=========

Ansible Role for creating Selfsigned certificates

Requirements
------------

- Ubuntu 20.04
- Ubuntu 18.04

Role Variables
--------------

see defaults/main.yml for more details


Example Playbook
----------------
1. Register client in your inventory file ../hosts.
```
[cert_selfsigned]
server-01
```

2. Set the default variable(s) for the group "cert_selfsigned" in "group_vars/cert_selfsigned.yml".
```
---
# Title: cert_selfsigned
#
# Author: Bitfinity-NL
# File: group_vars/cert_selfsigned.yml
#
# Description:
#   Default settings for selfsigned certificatess
#
def_cert_state      : 'enabled'
def_cert_base_path  : '/opt/ansible/system/ssl'
def_cert_days       : '365'
def_cert_rsa        : '4096'
def_cert_keyout     : '{{ def_cert_base_path }}/private/{{ ansible_hostname }}/apache-self>
def_cert_out        : '{{ def_cert_base_path }}/certs/{{ ansible_hostname }}/apache-selfsi>
def_cert_chain      : '{{ def_cert_base_path }}/chain/{{ ansible_hostname }}/chain.pem}}'
def_cert_country    : '<Country code (2 letters)>'
def_cert_state_prov : '<Province>'
def_cert_locality   : '<Place>'
def_cert_orgname    : '<organizational name>'
def_cert_orgunit    : '<department>'
def_cert_email      : '<email@example.com>'
```

3. Add the role to your playbook under the section "- roles".
```
- hosts: servers
  
  roles:
    - app-cert-selfsigned
```
 
License
-------

GPLv3

Author Information
------------------

Bitfinity-NL \
http://www.bitfinity.nl
