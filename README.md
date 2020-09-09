ansible-role-postgres
=====================

![](https://github.com/kevincoakley/ansible-role-postgres/workflows/Molecule%20Test/badge.svg)

Install Postgres 10, 11 or 12. Tested with Postgres 10, 11 and 12 on CentOS 7, CentOS 8, Ubuntu 18.04, Ubuntu 20.04.

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
          - type: local
            database: all
            user: all
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