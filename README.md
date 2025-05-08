vivaldi
=======
[![Ansible Lint](https://github.com/oxivanisher/role-vivaldi/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/oxivanisher/role-vivaldi/actions/workflows/ansible-lint.yml)

This role installs the vivaldi browser and sets it as default app for supported mit types.

**Note**: Analyzing the `DEBIAN/postinst` and the created daily cron job `/etc/cron.daily/vivaldi` from a vivaldi `.deb` shows that it creates a `/etc/apt/sources.list.d/vivaldi.list` file. It seems to ensure correct repo keys (which is good), but might fight with the deb822 repository. It seems, that the cron job does nothing, if the `.list` file is absent. Due to this situation, this role does the following:
1) Create a (modern) `/etc/apt/sources.list.d/vivaldi.sources` file
1) Install vivaldi from the repo
1) Remove the superfluous `/etc/apt/sources.list.d/vivaldi.list` file just created by the installer
Currently it seems, that the cron job will not re-create the `/etc/apt/sources.list.d/vivaldi.list` file.

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
