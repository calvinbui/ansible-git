[![Build Status](https://travis-ci.com/calvinbui/ansible-git.svg?branch=master)](https://travis-ci.com/calvinbui/ansible-git)

# Ansible Git

Install the latest upstream Git and configure Git config

##  Requirements

N/A

## Role Variables

`git_config` is in the syntax:

```yaml
git_config:
  - name: setting
    value: value of setting
    scope: local/scope/system (default)
    repo: if scope is local, provide path to repo
  ...
```

e.g.

```yaml
git_config:
  - name: user.name
    value: foo
    scope: global
  - name: user.email
    value: foo@example.com
    scope: local
    repo: /tmp/gists
```

## Dependencies

N/A

## Example Playbook

```yaml
- hosts: servers
  become: true
  pre_tasks:
    - name: Update apt cache.
      apt:
        update_cache: true
        cache_valid_time: 600
      changed_when: false
  roles:
   - role: ansible-git
```

## License

GPLv3

## Author Information

http://calvin.me
