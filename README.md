Ansible Role: chrony
====================

[![Build Status](https://travis-ci.org/chusiang/chrony.ansible.role.svg?branch=master)](https://travis-ci.org/chusiang/chrony.ansible.role) [![Ansible Galaxy](https://img.shields.io/badge/role-chrony-blue.svg)](https://galaxy.ansible.com/chusiang/chrony/) 

An Ansible role of setup chrony in everyway.

Requirements
------------

None.

Role Variables
--------------

```
# All
#####

# Allow access range of subnet or node, like 10.8.0.0/16, 192.168.1.24.
chrony_allow_range: ''

# Debian & Ubuntu
#################

apt_chrony_package:   'chrony'
apt_chrony_conf:      '/etc/chrony/chrony.conf'
apt_chrony_ntp_server:
  - '2.debian.pool.ntp.org'
apt_chrony_keyfile:   '/etc/chrony/chrony.keys'
apt_chrony_driftfile: '/var/lib/chrony/chrony.drift'
apt_chrony_logdir:    '/var/log/chrony'

# EL
####

yum_chrony_package:   'chrony'
yum_chrony_conf:      '/etc/chrony.conf'
yum_chrony_ntp_server:
  - '0.centos.pool.ntp.org'
  - '1.centos.pool.ntp.org'
  - '2.centos.pool.ntp.org'
  - '3.centos.pool.ntp.org'
yum_chrony_keyfile:   '/etc/chrony.keys'
yum_chrony_driftfile: '/var/lib/chrony/drift'
yum_chrony_logdir:    '/var/log/chrony'
```

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: chusiang.chrony }

License
-------

Copyright (c) chusiang from 2018 under the MIT license.
