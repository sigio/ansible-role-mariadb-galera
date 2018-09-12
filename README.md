Mariadb/Galera
==============

Install mariadb with galera support on Ubuntu LTS or CentOS/RHEL 7.x

Requirements
------------

On CentOS/RedHat and Ubuntu/Debian the mariadb packages from mariadb.org are used. (I've tried with the software-collections version for RHEL 7, but couldn't get them to build a galera cluster)

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

  - hosts: galera-db-servers
    roles:
      - common
      - mariadb-galera
    vars:
          - galera_wsrep_cluster_name: galera-cluster-1
          - galera_wsrep_cluster_address: "gcomm://{{ foo_IP }},{{ bar_IP }},{{ baz_IP }}"
          - mariadb_conf_dir: "/etc/mysql/conf.d"
          - wsrep_node_address: "{{ node_IP }}" # optional makes sense only if it's not ansible_default_ipv4.address
          - mariadb_install_xtrabackup: true  # optional
          - mariadb_install_backupninja: true # optional
          - ufw_enabled: false                # optional


License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
