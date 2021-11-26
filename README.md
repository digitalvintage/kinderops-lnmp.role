KinderOps-LNMP
=========

An example role for deploying an LNMP (Linux/Nginx/Php-fpm/MariaDB) server. A part of KinderOps educational project.

Example Playbook
----------------
---
- hosts: all
  vars_files:
    - "vars/{{ inventory_hostname }}.yml"
  roles:
    - { role: kinderops-lnmp.role, tags: common }

Example Host Vars File
----------------
# vars for kindermaster host---

# Settings for default/first vhost
default_vhost_name: host-1.kinderops.ru
default_vhost_add_www: false
default_vhost_dbname: host-1-db
default_vhost_dbuser: host-1
default_vhost_dbpass: password
default_vhost_app: wordpress

# Additional vhosts and settings
# If not set - will be copied from default
vhosts:
  - vhost_name: host-2.kinderops.ru
    vhost_add_www: false
    vhost_dbname: host-2-db
    vhost_dbuser: host-2
    vhost_dbpass: password
    vhost_app: joomla

  - vhost_name: pumanevalit.kinderops.ru
    vhost_add_www: false
    vhost_dbname: host-3-db
    vhost_dbuser: host-3
    vhost_dbpass: password
    vhost_app: test


License
-------

BSD

Author Information
------------------

Written by Vitaly Prokofiev
