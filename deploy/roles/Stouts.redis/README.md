Stouts.redis
============

[![Build Status](https://travis-ci.org/Stouts/Stouts.redis.png)](https://travis-ci.org/Stouts/Stouts.redis)

Ansible role which manage redis

#### Variables

```yaml
redis_enabled: yes                      # Enable the role
redis_service: redis-server             # Name of the redis service
redis_configuration: /etc/redis/redis.conf  # Path to redis configuration
redis_update_kernel: yes                # Set the kernel parameter for vm overcommit 

# Setup redis role
redis_role: master
#If role is slave set these values too
redis_master_ip: 1.1.1.1
redis_master_port: 6379
redis_master_auth: None

# Setup redis options
redis_bind: "127.0.0.1"
redis_port: 6379
redis_syslog_enabled: "yes"
redis_databases: 4
redis_database_save_times:
  - [900, 1]
  - [300, 10]
  - [60, 10000]
redis_dbfilename: dump.rdb
redis_db_dir: /var/lib/redis
redis_requirepass: false
redis_pass: None
redis_max_clients: 128
redis_max_memory: 512mb
redis_maxmemory_policy: volatile-lru
redis_appendfsync: everysec
```

#### Usage

Add `Stouts.redis` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.redis

  vars:
    redis_bind: 0.0.0.0
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.redis/issues)!
