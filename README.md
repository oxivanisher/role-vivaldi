vivaldi
=======
[![Ansible Lint](https://github.com/oxivanisher/role-vivaldi/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/oxivanisher/role-vivaldi/actions/workflows/ansible-lint.yml)

This role installs the vivaldi browser and sets it as default app for supported mit types.


Role Variables
--------------

| Name          | Comment                              | Default value |
|---------------|--------------------------------------|---------------|
| vivaldi_os_users  | Users for which vivaldi will be set the default app for.  | `[]`          |

Example Playbook
----------------
```yaml
- name: Install vivaldi
  hosts: client
  collections:
    - oxivanisher.linux_desktop
  roles:
    - role: oxivanisher.linux_desktop.vivaldi
```

License
-------

BSD

Author Information
------------------

This role is part of the [oxivanisher.linux_desktop](https://galaxy.ansible.com/ui/repo/published/oxivanisher/linux_desktop/) collection, and the source for that is located on [github](https://github.com/oxivanisher/collection-linux_desktop).
