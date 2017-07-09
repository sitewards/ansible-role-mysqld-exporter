# Ansible Prometheus mysqld-eexporter

This is the Ansible Prometheus mysqld-exporter role. It's designed for consumption by playbooks, not for consumption by
itself. It adds the Prometheus mysqld-exporter, bound to localhost. It's expected that another role will take care of
reverse proxying this exporter with SSL and auth.

## Requirements

- Internet Access

## Usage

Include this in another ansible playbook. For sample, consider a generic server playbook:

```
---
# $PLAYBOOK_ROOT/server.yaml
- name: "server"
  hosts: all
  become: true
  become_user: "root"
```

Add the reference for the role:

```
# $PLAYBOOK_ROOT/server.yaml
# ...
become_user: "root"
roles
  - "mysqld-exporter"
```

This will allow the role to be discovered. Then, add this repo as a submodule:

```
$ cd path/to/playbook/root
$ mkdir roles/
$ git submodule add https://github.com/sitewards/ansible-role-mysqld-exporter roles/node-exporter
```

This should work!

## Configuration

The variables that are available are defined in defaults/main.yml

## Contact

- https://www.sitewards.com/
