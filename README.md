# Ansible Role: Drush

[![Build Status](https://img.shields.io/travis/rwanyoike/ansible-role-drush.svg)](https://travis-ci.org/rwanyoike/ansible-role-drush) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/rwanyoike/ansible-role-drush/master/LICENSE)

Installs and configures Drush on RHEL/CentOS ~~or Debian/Ubuntu~~.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
drush_git_version: master
drush_git_update: false
drush_git_force_update: false

drush_install_dir: /usr/local/share/drush
drush_exec: /usr/local/bin/drush
# These options are the safest for avoiding GitHub API rate limits, but builds
# can be sped up substantially by changing to --prefer-dist
drush_composer_cli_options: --prefer-source --no-interaction
```

## Dependencies

- rwanyoike.git (https://github.com/rwanyoike/ansible-role-git)
- rwanyoike.composer (https://github.com/rwanyoike/ansible-role-composer)

## Example Playbook

```yaml
- hosts: servers

  vars_files:
    - vars/main.yml

  roles:
    - role: rwanyoike.drush
```

Inside `vars/main.yml`:

```yaml
drush_composer_cli_options: --prefer-dist --no-interaction

# ... etc ...
```

## License

MIT

## Author Information

- This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
- This role was forked in 2015 by [Raymond Wanyoike](https://github.com/rwanyoike).
