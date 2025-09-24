# Ansible Role: keepalived

To include this role in your ansible repository, add the following to  `./requirements.yml` in your repository:

```yaml
- name: <role-name>
  src: git+ssh://git@github.com/< user/org >/iac.ansible-role.<role-name>.git
  version: <version>
```

# Description

This ansible role install and configures keepalived

## Usage

explain in detail how and when your role should or should not be used and describe all functions and common use cases.


## Role Variables

```yaml
keepalived_vrrp_interface: "{{ ansible_default_ipv4.interface }}"
keepalived_dummy_number: 0
keepalived_global_state: "MASTER"
keepalived_global_prio: 100
keepalived_package: keepalived
keepalived_version: # if this is defined, keepalived package will also be pinned to this specific version

keepalived_sync_groups:
  <name>:
    instances:
      - <instance>
    notify_script:
    notify_master:
    notify_backup:
    notify_fault:

keepalived_scripts:
  <name>:
    check_script:
    interval: 5
    fall: 3
    rise: 6
    timeout:
    weight:

keepalived_instances:
  <name>:
    interface:
    state: "{{ keepalived_global_state }}"
    virtual_router_id:
    priority: "{{ keepalived_global_priority }}"
    noopreempt: # bool
    preempt delay: # seconds 0-1000
    accept_mode: # bool
    authentication_password:
    unicast_src_ip: "{{ hostvars[inventory_hostname]['ansible_'~keepalived_vrrp_interface].ipv4.address }}"
    unicast_peers:
      group: #ansible group
      servers:
        -
    vips:
      - address:
        device: "{{ keepalived_vrrp_interface }}"
    virtual_routes:
      - <route>
    track_scripts:
      - <script>
    track_interfaces:
      - <interface>
    notify_script:
    notify_master:
    notify_backup:
    notify_fault:
    notify_stop:

keepalived_virtual_servers:
  - ip:
    port:
    ip_family: 'inet'
    delay_loop:
    lvs_sched: 'rr'
    lvs_method: 'DR'
    protocol: 'TCP'
    ha_suspend: #bool
    real_servers:
      - ip:
        port:
        misc_check:
          misc_path:
          misc_timeout:
          warmup:
          misc_dynamic: bool
```

## Example Playbook

provide an example of how to implement this role in a playbook. provide multiple examples if use cases differ largely

```yaml
- name: execute my role
  hosts: <group of hosts>
  gather_facts: true
  roles:
    - role: my_role
```

---
> ℹ️ This ansible role adheres to the [Coven913 ansible role template](https://github.com/coven913/template.ansible-role).