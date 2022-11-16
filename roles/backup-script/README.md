# backup-script

This role creates cron task that creates an encrypted backup and push it on an openstack storage every day at 2AM.

## Options

- `enable_backup`: not used in the role but convenient to disable backup in dev env

See `argument_specs.yml`.

## Example usage

```yaml
// playbook.yml

- role: backup-script
  tags: backup-script
  when: enable_backup
```

```yaml
// vars.yml

backup_user: '{{ app_user }}'
backup_identifier: api-auth-database
gpg_recipient: contact@api.gouv.fr
frequency: daily
enable_backup: true
public_pgp_key_path: './pgp-keys/{{ inventory_file | basename }}/backup.pub.asc'
backup_command: 'pg_dump --clean --format=custom {{ pg_database }}'
# for folder backup you can use:
# backup_command: "tar --create --gzip --absolute-names {{ folder_to_backup }}
openstack_password: 012345ABCDEabcdefghijklmnopqrstu
openstack_username: user-0123ABCDabcd
```

```yaml
// secrets.yml

openstack_tenant_id: 01234567890123456789abcdeabcdeab
openstack_tenant_name: 0123456789012345
openstack_password: 012345ABCDEabcdefghijklmnopqrstu
openstack_username: user-0123ABCDabcd
```
