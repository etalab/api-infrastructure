# team-ssh-keys

This roles adds the `team_ssh_keys` ssh keys to the `target_users` so that the team members can connect as these users on the target host.
It also hardens the ssh options to only allow ssh connection to these users.

## Options

- `target_users`: list of users to add the ssh keys to
- `team_ssh_keys`: list of ssh keys to add to the target_users. Can be the ssh key itself or a link to the ssh key ie `https://github.com/user.keys`
