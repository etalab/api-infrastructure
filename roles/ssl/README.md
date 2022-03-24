# ssl

This role installs certbot, create new certificates if applicable, and adds a renew cron.

This role uses ovh API for dns validation.

## Dependencies

- geerlingguy.certbot

## Options

See `argument_specs.yml`.

## Example usage

```yaml
// playbook.yml

- hosts: all
  roles:
    - ssl
```

```yaml
// vars.yml

ssl_certbot_admin_email: contact@api.gouv.fr
ssl_ovh_zone: api.gouv.fr
ssl_certbot_certs:
  - email: janedoe@example.com
    webroot: "/var/www/html/"
    domains:
      - example1.com
      - example2.com
  - domains:
      - api.gouv.fr
```

```yaml
// secrets.yml

ssl_ovh_dns_api_app_key: xxx
ssl_ovh_dns_api_app_secret: xxx
ssl_ovh_dns_api_consumer_key: xxx
```
