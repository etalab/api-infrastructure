# ssl

This role installs certbot, create new certificates if applicable, and adds a renew cron.

This role uses ovh API for dns validation.

## Options

- `ssl_certbot_admin_email`: self-explanatory
- `ssl_certbot_auto_renew_user`: self-explanatory
- `ssl_certbot_auto_renew_minute`: cron
- `ssl_certbot_auto_renew_hour`: cron
- `ssl_certbot_create_if_missing`: if true, roles will create a certficate when no cert is present
- `ssl_certbot_create_command`: certbot create and renew command
- `ssl_ovh_zone`: ovh API zone
- `ssl_ovh_endpoint`: ovh API endpoint

## Secrets

- `ovh_dns_api_app_key`: OVH API key
- `ovh_dns_api_app_secret`: OVH API secret
- `ovh_dns_api_consumer_key`: OVH API consumer key

## Example usage

```yaml
// playbook.yml

- hosts: all
  roles:
    - ssl
```

```yaml
// vars.yml

ssl_ovh_zone: api.gouv.fr
ssl_ovh_endpoint: ovh-eu
ssl_certbot_admin_email: contact@api.gouv.fr
ssl_certbot_auto_renew_user: "{{ ansible_user }}"
certbot_certs:
  - domains:
      - https://api.gouv.fr
```

```yaml
// secrets.yml

ovh_dns_api_app_key: xxx
ovh_dns_api_app_secret: xxx
ovh_dns_api_consumer_key: xxx
```
