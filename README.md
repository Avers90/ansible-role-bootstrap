# ansible-role-bootstrap

Prepares a fresh VPS for Ansible by installing Python.

## Requirements

- SSH access to the host (root with password for fresh VPS)
- Debian/Ubuntu

## Role Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `bootstrap_python_packages` | `[python3, python3-apt]` | Packages to install |

## Usage
```yaml
- hosts: all
  become: true
  gather_facts: false
  roles:
    - ansible-role-bootstrap
```

## Notes

This role must run with `gather_facts: false` because facts 
require Python which may not be installed yet.
