# backup-script

This role creates cron task that creates an encrypted backup and push it on an openstack storage every day at 2AM.

## Options

- `enable_backup`: not used in the role but convenient to disable backup in dev env
- `frequency`: can be `daily` or `weekly`
- `backup_user`: the role become this user to create the backup
- `backup_identifier`: use in the name the backup file and the backup script
- `backup_command`: this bash command should output the backup in STDOUT, it will be piped in the gpg encryption command.
- `backup_environment`: use in the name of the backup file
- `gpg_recipient`: email used in the gpg encryption process
- `public_pgp_key_path`: local path to the pgp public keys
- `openstack_auth_url`: openstack config
- `openstack_identity_api_version`: openstack config
- `openstack_region_name`: openstack config
- `openstack_container_name`: openstack config
- `openstack_username`: openstack config
- `openstack_tenant_id`: openstack config
- `openstack_tenant_name`: openstack config
- `openstack_password`: openstack config
- `openstack_username`: openstack config
- `openstack_password`: openstack config

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
public_pgp_key_path: '{{ inventory_dir }}/pgp-keys/{{ inventory_file | basename }}/backup.pub.asc'
backup_command: 'pg_dump --clean --format=custom {{ pg_database }}'
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
