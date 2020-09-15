ASBRL-POSTGRESQL
=========

Deploy a single PostgreSQL node as a Docker container.

Requirements
------------

Need to be Docker engine installed.

Role Variables
--------------

- default_user: 'ubuntu'
- ROOT_USERNAME: 'postgres'
- ROOT_PASSWORD: 'Pa$$w0rd'
- BUILD: '12'
- LISTEN_ADDRESSES: '*'
- PORT: 5432
- MAX_CONNECTIONS: 100
- SHARED_BUFFERS: '128MB' # 15-25% of Total RAM
- WAL_BUFFERS: '4MB' # 3% of shared_buffers
- EFFECTIVE_CACHE_SIZE: '512MB' # 50-75% of Total RAM.
- WORK_MEM: '4MB' # 25% of Total RAM / max_connections
- MAINTENANCE_WORK_MEM: '64MB' # 5% of Total RAM

Dependencies
------------

None

Example Playbook
----------------

      - name: Deploy PostgreSQL
        include_role:
          name: asbrl-postgresql
        vars:
          ROOT_USERNAME: "{{ PG_ROOT_USERNAME }}"
          ROOT_PASSWORD: "{{ PG_ROOT_PASSWORD }}"
        tags:
          - postgres

License
-------

BSD

Author Information
------------------

Moegui.com