# python_dev

An Ansible role to install UV (the extremely fast Python package installer and resolver) if not already present.

## Requirements

- curl must be available on the target system
- Internet access to download UV installer

## Role Variables

See `defaults/main.yml` for available variables.

## Dependencies

None

## Example Playbook

```yaml
- hosts: development
  roles:
    - role: python_dev
```

## License

MIT