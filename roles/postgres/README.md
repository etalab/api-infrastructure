# postgres

This role installs postgres, create new user and new database.

It can also install postgres extensions.

## Options

See `argument_specs.yml`.

## Example usage

```yaml
# playbook.yml

- hosts: all
  roles:
    - postgres
```

```yaml
# vars.yml

pg_user: datapass
pg_database: datapass
pg_extensions:
  - intarray
```

```yaml
# secrets.yml

pg_password: xxx
```
