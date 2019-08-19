ansible-role-postgres
=====================

[![Build Status](https://travis-ci.org/kevincoakley/ansible-role-postgres.svg?branch=master)](https://travis-ci.org/kevincoakley/ansible-role-postgres)

Install Postgres 10 or 11. Tested with Postgres 10 and 11 on CentOS 7 and Ubuntu 18.04.

Requirements
------------

None

Role Variables
--------------

See defaults/main.yml and the example inventory below

Dependencies
------------

None

Example Playbook
----------------
  
    - name: Postgres role 
      hosts: postgres
      become: yes
      become_method: sudo
    
      vars:
        - postgres_listen_addresses: "*"
        - postgres_client_auth:
          - type: host
            database: all
            user: all
            address: 0.0.0.0/0
            method: md5
    
      roles:
        - ansible-role-postgres
    
      tags:
        - postgres

License
-------

BSD

Author Information
------------------

Kevin Coakley (https://github.com/kevincoakley)