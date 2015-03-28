# Ansible Role: Liquidprompt

[![Build Status](https://travis-ci.org/sbani/ansible-role-liquidprompt.svg)](https://travis-ci.org/sbani/ansible-role-liquidprompt)
[![Galaxy](http://img.shields.io/badge/galaxy-sbani.liquidprompt-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/3254)

Ansible Role that installs and enables [liquidprompt](https://github.com/nojhan/liquidprompt) (lp)

## Usage
### Default
The default behaviour is an activation for the *vagrant* user only without any extra configuration.
### Activate lp for all users
This will update */etc/bash.bashrc*. The list *liquidprompt_apply_to_users* won't be used if *liquidprompt_apply_all_users* is true
```yaml
# Apply liquidprompt to all users
liquidprompt_apply_all_users: true

# Activate for the following users
#liquidprompt_apply_to_users:
#  - vagrant
```
### Activate lp for specific user (list)
This will add lp to the home of the users in list. *liquidprompt_apply_all_users* neds to be set to false.
```yaml
# Apply liquidprompt to all users
liquidprompt_apply_all_users: false

# Activate for the following users
liquidprompt_apply_to_users:
  - vagrant
  - web
  - user1
```
### Add own liquidprompt config
lp as a high number of options you can use. Please take a look in the lp repo for more informations. Here's an example:
```yaml
# Custom config for liquidpropt
liquidprompt_enable_custom_variables = true
liquidprompt_custom_variables:
  - LP_PS1_POSTFIX="\n $ " # Add new line before input
  - LP_PS1_PREFIX="\[\e]0;\u@\h: \w\a\]" # Custom window's title
```
## License
MIT
## Credits
Specials thanks goes to all liquidprompt contributors and the maintainers/original authors.
## Contribution / Discussion / Missing features
Contributors and patches are welcome! Open discussions about the defaults or other features you would like to have.
## Author Information
Sufijen Bani (http://www.sbani.net)