Role Name
=========

Install Prometheus Blackbox_Exporter from github repository

Requirements
------------

nope

Role Variables
--------------

all variables are defined in defaults:

```yaml
---
# defaults file for blackbox_exporter

prometheus_user: prometheus
prometheus_group: prometheus
prometheus_install_path: '/opt/prometheus'
prometheus_config_path: '/etc/prometheus'
prometheus_pid_path: '/var/run/prometheus'
prometheus_loglevel: 'info'

prometheus_blackbox_exporter_install_path: '{{ prometheus_install_path }}'
prometheus_blackbox_exporter_config_path: '{{ prometheus_config_path }}'
prometheus_blackbox_exporter_pid_path: '{{ prometheus_pid_path }}'
prometheus_blackbox_exporter_user: '{{ prometheus_user }}'
prometheus_blackbox_exporter_group: '{{ prometheus_group }}'
prometheus_blackbox_exporter_loglevel: '{{ prometheus_loglevel }}'
prometheus_blackbox_exporter_listen: '{{ prometheus_blackbox_exporter_listen_ip }}:{{ prometheus_blackbox_exporter_listen_port }}'
prometheus_blackbox_exporter_listen_port: '9115'
prometheus_blackbox_exporter_listen_ip: ''
prometheus_blackbox_exporter_version: '0.14.0'
prometheus_blackbox_exporter_config: 'blackbox.yml'

enable_ufw: false
prometheus_blackbox_exporter_src_access:
  - "{{ ansible_default_ipv4.network }}/{{ ansible_default_ipv4.netmask }}"
```

For typical deployment you can eventually define enable ufw fw and define src access list
Based on defined variables you can set variables common for all prometheus stack

Dependencies
------------

If you want to set fw, you need to have ufw role

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
    - hosts: servers
      roles:
         - role: blackbox_exporter
```

License
-------

BSD

Author Information
------------------

Tomasz Baczynski

