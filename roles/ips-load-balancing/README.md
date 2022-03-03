# Ips load balancing

This role adds multiple outgoing IPs

## Example usage

```yaml
// playbook.yml

- hosts: all
  roles:
    - ips-load-balancing
```

```yaml
// vars.yml
---
outgoing_ips:
  - xx.yy.zz.00
  - xx.yy.zz.10
  - xx.yy.zz.20
  - xx.yy.zz.30
```
