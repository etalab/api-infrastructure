# nginx

This role installs nginx, set up the default http conf, set up a redirect from http to https and add a conf to blacklist ips.

## Options

See `argument_specs.yml`.

## Example usage

```yaml
// playbook.yml

- hosts: all
  roles: nginx
```

```yaml
// vars.yml

blacklisted_ips:
  - 192.168.0.1
  - 127.0.0.1
```
