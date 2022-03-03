# Refresh apt-cache

This role refresh apt cache

## Example usage

```yaml
// playbook.yml

- hosts: all
  roles:
    - refresh-apt-cache
```

```yaml
// vars.yml

apt_cache_valid_time: 86400
```
