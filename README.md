Ansible-openbao
=========

An ansible role to install and configure openbao. Openbao is an open source solution to manage, store, and distribute sensitive data including secrets, certificates, and keys.

For full config description and params, look at https://github.com/openbao/openbao/tree/main/website/content/docs/configuration

Requirements
------------

Internet connection on the server where the application is installed, because the role downloads the package from the officiall OpenBao GitHub releases.

Role Variables
--------------

- `openbao_version` - The version of OpenBao to install (default: `2.1.1`)

- `openbao_enable_ui` - Enable web UI (default: `false`)

- `openbao_api_addr` - API endpoint listen address (default: empty string)

- `openbao_cluster_addr` - Cluster listen address (default: empty string)

- `openbao_storage_type` - Storage backend type (default: `file`)

- `openbao_storage_params` - Storage backend configuration parameters:
  - `path` - Path for file storage, in the file backend scenario (default: "/opt/openbao/data")

- `openbao_listeners` - List of listener configurations:
  ```yaml
  - type: tcp
    params:
      address: 0.0.0.0:8200
      cluster_address: 0.0.0.0:8201
      tls_cert_file: "/opt/openbao/tls/tls.crt"
      tls_key_file: "/opt/openbao/tls/tls.key"

Dependencies
------------

No dependencies.

Example Playbook
----------------

Minimal usage:
```yaml
    - hosts: all
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