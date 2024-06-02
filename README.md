# modules

## Description

Load kernel modules and enable load at boot time.

## Settings

``` yaml
modules:
  - {name: module1_name, state: present, arg: 'a=1'}
  - {name: module2_name, state: absent}
```

The state and arg is optional parameter. By default state=present. Arg parameter will be added in `/etc/modules` file as argument for module.

## Examples

### Modules for docker in LXC

``` yaml
- role: modules
  modules:
    - {name: overlay}
    - {name: br_netfilter}
    - {name: ip_vs}
```

### Disable modules

```yaml
- role: modules
  modules:
    - {name: overlay, state: absent}
    - {name: br_netfilter, state: absent}
    - {name: ip_vs, state: absent}
```

Changes affect modules enabled by role only, and changes will apply after server reboot.

## TODO

- tests
