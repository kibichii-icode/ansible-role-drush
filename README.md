# Ansible Role: Drush

[![Build Status](https://img.shields.io/travis/thestarkenya/ansible-role-drush.svg)](https://travis-ci.org/thestarkenya/ansible-role-drush) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/thestarkenya/ansible-role-drush/master/LICENSE)

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

- ansible-role-git (https://github.com/thestarkenya/ansible-role-git)
- ansible-role-composer (https://github.com/thestarkenya/ansible-role-composer)

## Example Playbook

```yaml
- hosts: servers

  vars_files:
    - vars/main.yml

  roles:
    - role: ansible-role-drush
```

Inside `vars/main.yml`:

```yaml
drush_composer_cli_options: --prefer-dist --no-interaction

# ... etc ...
```

## License

MIT
