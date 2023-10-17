Ansible Role: Primary DC
=========

An Ansible role to prepare a primary Domain Controller and create a new forest.

Requirements
------------

None.

Role Variables
--------------

```yml
domain_admin_user: 'Administrator'
domain_admin_password: 'Password!'
domain_name: ad01.bufu-sec.com
netbios_name: AD01
domain_password: Password!
ntp_servers: "0.de.pool.ntp.org,1.de.pool.ntp.org"
reverse_dns_zone: "192.168.91.0/24"
dns_forwarders:
  - "192.168.91.1"
required_psmodules:
  - xPSDesiredStateConfiguration
  - NetworkingDsc
  - ComputerManagementDsc
  - ActiveDirectoryDsc
required_features: 
  - AD-domain-services
  - DNS
```

Dependencies
------------

None.

Example Playbook
----------------

```yml
- hosts: pdc01
  roles:
    - role: xbufu.ad_pdc
      vars:
        domain_name: ad01.bufu-sec.com
        netbios_name: AD01
        domain_password: Password!
        reverse_dns_zone: "192.168.91.0/24"
        reverse_dns_zone: "192.168.91.0/24"
        dns_forwarders:
          - "192.168.91.1"

```

License
-------

MIT / BSD

Author Information
------------------

Created by xbufu.
