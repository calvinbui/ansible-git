# Ansible Git

Install the latest upstream Git and configure Git config

##  Requirements

N/A

## Role Variables

`git_config` is in the syntax:
```
git_config:
  setting:
    - value: value of setting
    - scope: local/scope/[system]
    - repo: if scope is local, provide path to repo
```

e.g.

```
git_config:
  user.name:
    value: foo
    scope: global
  user.email:
    value: foo@example.com
    scope: local
    repo: /tmp/gists
```

## Dependencies

N/A

## Example Playbook

```
  - hosts: servers

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
