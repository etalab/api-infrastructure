# Ansible Collection - etalab.api_infrastructure

This collection is currently used by the following projects:

- [Auth-api](https://github.com/betagouv/api-auth)
- [Datapass](https://github.com/betagouv/datapass)
- [Annuaire des Entreprises](https://github.com/etalab/annuaire-entreprises-site)
- [api.gouv.fr](https://github.com/betagouv/api.gouv.fr)

The aim is to share the best roles found in every Etalab project, to make them re-usable and easy to use.

## How ready is the role?

- 0 = not sharable
- 1 = optional variables are defaulted
- 2 = there is a README.md
- 3 = there is an arguments spec
- 4 = the role is tested with molecule
- 5 = the role is tested with e2e test (provisioning actual machines like https://github.com/geerlingguy/mac-dev-playbook/blob/master/.github/workflows/ci.yml)

## Role list

| name                  | status |
|-----------------------|--------|
| authorized-ssh-keys   | 3      |
| backup-script         | 3      |
| ssl                   | 3      |
| ips-load-balancing    | 2      |
| refresh-apt-cache     | 2      |
| redis                 | 2      |
| ssh-security          | 2      |
| postgres              | 0      |
| app-deployment        | 0      |
| app-user              | 0      |
| continuous-deployment | 0      |
| nginx                 | 0      |
| node-app              | 0      |
| ufw                   | 0      |
