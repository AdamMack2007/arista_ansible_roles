# Configure NTP

Configures NTP servers using the "management" VRF but can be modified. Can be used to remove non-compliant NTP servers by enabling "enforce_compliance" in defaults/main.yml

## Role Variables

- **ntp_servers**: List of NTP servers to configure
- **ntp_vrf**: VRF to configure the NTP servers with. If left blank it will not use a VRF.
- **enforce_compliance**:(yes/no) Whether to remove NTP servers that are not in the ntp_servers list.

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

```
- name: Configure NTP
  hosts: all
  gather_facts: no

  roles:
    - config_ntp

```

## License

BSD
