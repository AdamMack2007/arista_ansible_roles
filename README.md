# Arista Base Configuration

Ansible network roles to perform a base configuration of Arista EOS devices

## Usage

Role name and functions:

- **config_aaa**: Configure authentication/authorization settings on devices.
- **config_acl**: Create/update management ACLs.
- **config_credentials**: Update user credentials for local accounts
- **config_dns**: Configures DNS servers
- **config_ntp**: Configures NTP servers
- **config_provisioning**: Configures misc changes: hostnames, ssh ciphers, enabling API and login banners.
- **config_save**: Simple playbook to save the running configurations.
- **config_snmp**: Configures SNMPv3 on devices.
- **config_syslog**: Configures remote/local syslog settings.
- **facts**: Gather facts for arista devices

## Information

Each role has a readme with the variables or information required as well as any recommendations.

## Example playbook

Configure just NTP servers

```
- name: Configure NTP Servers
  hosts: all
  gather_facts: no

  roles:
    - config_ntp
```

Include all roles to build the entire base configuration

```
- name: Arista Base Configuration
  hosts: all
  gather_facts: no

  roles:
    - facts
    - config_provisioning
    - config_acl
    - config_dns
    - config_ntp
    - config_snmp
    - config_syslog
    - config_save
    - config_credentials
    - config_aaa
```

## Recommendations

I strongly recommend testing in a lab first to ensure the changes comply with your desired state.
