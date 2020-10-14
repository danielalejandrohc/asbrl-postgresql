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
- DOCKER_NAME: 'postgres'
- DOCKER_CPU_PERIOD: 0
- DOCKER_CPU_QUOTA: 0
- DOCKER_MEMORY: 0
- CONTAINER_STATE: 'started'
- VOLUME_STATE: 'present'

Dependencies
------------

None

Example Playbook
----------------

    - name: Deploy PostgreSQL
      include_role:
        name: asbrl-postgresql
      vars:
        ROOT_USERNAME: "posgresql"
        ROOT_PASSWORD: "Pa$$W0rd"
        DOCKER_CPU_QUOTA: 100000
        DOCKER_MEMORY: 1G
      tags:
        - postgres

License
-------

BSD

Author Information
------------------

Moegui.com