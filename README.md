Role Name 
=========

Ansible role to setup a Ubuntu Primary Active Directory Domain Controller

Requirements 
------------ 

- Ansible control server
- Ubuntu

Role Variables 
--------------

You can override these variable(s) in your own playbook

- smb_workgroup   : TEST
- smb_realm       : TEST.NET
- smb_dns_servers : "{{ ansible_default_ipv4.address }}"
- smb_username    : administrator 
- smb_password    : Welkom123



Example Playbook 
----------------

   - hosts: dc01
     become: true

     vars:
       # Samba4 AD
       smb_workgroup : TEST
       smb_realm     : TEST.NET 
       smb_username  : administrator
       smb_password  : Password123

     roles:
       - ansible-role-samba4-primary-ad-dc

License 
-------

GNU GPLv3

Author Information 
------------------

www.bitfinity.nl
