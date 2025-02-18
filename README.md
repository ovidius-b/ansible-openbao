Ansible-openbao
=========

An ansible role to install and configure openbao. Openbao is an open source solution to manage, store, and distribute sensitive data including secrets, certificates, and keys.

For full config description and params, look at https://github.com/openbao/openbao/tree/main/website/content/docs/configuration

Requirements
------------

Internet connection on the server where the application is installed, because the role downloads the package from the officiall OpenBao GitHub releases.

Role Variables
--------------



Dependencies
------------

No dependencies.

Example Playbook
----------------

Minimal usage:
```yaml
    - hosts: all
      remote_user: ansibot
      become: true

      roles:
        - role: ansible-openbao
```

License
-------

MIT

Author Information
------------------

Ovidiu Bratosin
https://wipsquare.dev