# Configure Provisioning

Provisions miscellaneous tasks as listed below:

- Configures hostname
- Configures login banner
- Configures SSH ciphers to only allow AES256
- Enables/Disables the eAPI

## Requirements

A file called banner.txt is required in the files directory of this role. The name, location and contents of the file can be changed but must be updated in the task if the former 2 changes are made.

## Role Variables

- **enable_api**:(yes/no) Whether to enable the eAPI

## Example Playbook

```
- name: Configure Provisioning
  hosts: all
  gather_facts: no

  roles:
    - config_provisioning
```

## License

BSD
