Role Name 
=========

Ansible role to setup a Ubuntu Primary Active Directory Domain Controller

Requirements 
------------ 

- Ansible control server
- Ubuntu

Role Variables 
--------------

Set defaut variable(s) in group_vars for reusing in other playbooks.
-  def_ad_workgroup : 'LAB'
-  def_ad_realm     : 'LAB.LOCAL'
-  def_ad_admin     : 'administrator'
-  def_ad_pass      : 'Welkom123'
-  def_ad_dns       : '192.168.0.66 192.168.0.67'
-  def_ad_dc01      : '192.168.0.67'
-  def_ad_dc02      : '192.168.0.67'
-  def_ad_basedn    : 'OU=lab,DC=lab,DC=local'

You can override these variable(s) in your own playbook

- smb_workgroup   : TEST
- smb_realm       : TEST.NET
- smb_dns_servers : "{{ ansible_default_ipv4.address }}"
- smb_username    : administrator 
- smb_password    : Welkom123

Example Playbook 
----------------

    - hosts: adc01
      become: true

      vars:
        # -- Custom settings: role-samba4-primary-ad-dc --
        smb_workgroup : 'LAB'
        smb_realm     : 'LAB.LOCAL' 
        smb_username  : 'administrator'
        smb_password  : 'Password123'

      roles:
        - role-samba4-primary-ad-dc
 

License 
-------

GNU GPLv3

Author Information 
------------------

www.bitfinity.nl
