# team-ssh-keys

This roles adds the `authorized_ssh_keys` SSH keys to the specified users so that the team members can connect as different users on the target host.
It also hardens the ssh options to only allow ssh connection to these users.

## Options

- `authorized_ssh_keys`: a list of public SSH keys with their corresponding authorized users

## Example usage

```yaml
// playbook.yml

- hosts: all
  roles:
    - authorized-ssh-keys
```

```yaml
// vars.yml

authorized_ssh_keys:
    - key: https://github.com/username.keys
      users:
        - "{{ app_user }}"
        - "{{ ansible_user }}"
    - key: "{{ deployment_key }}"
      users:
        - "{{ deployment_user }}"
```
