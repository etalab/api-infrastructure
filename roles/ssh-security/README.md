# team-ssh-keys

This role hardens the ssh options to only allow ssh connection to these users.

## Example usage

```yaml
# playbook.yml

- hosts: all
  roles:
    - ssh-security
```

```yaml
# vars.yml

# none
```
