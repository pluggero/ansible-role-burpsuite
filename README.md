# Ansible Role: Burpsuite

[![CI](https://github.com/pluggero/ansible-role-burpsuite/actions/workflows/ci.yml/badge.svg)](https://github.com/pluggero/ansible-role-burpsuite/actions/workflows/ci.yml) [![Ansible Galaxy downloads](https://img.shields.io/ansible/role/d/pluggero/burpsuite?label=Galaxy%20downloads&logo=ansible&color=%23096598)](https://galaxy.ansible.com/ui/standalone/roles/pluggero/burpsuite)

An Ansible Role that installs a basic configuration of burpsuite.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
burpsuite_version: "x.x.x"
```

The version of burpsuite to install can be defined in the variable `burpsuite_version`.

```yaml
burpsuite_edition: "community"
```

The edition of burpsuite to install can be defined in the variable `burpsuite_edition`.
It can be either `community` or `pro`.

```yaml
burpsuite_release_channel: "Stable"
```

The release channel of burpsuite to install can be defined in the variable `burpsuite_release_channel`.
It can be either `Stable` or `Early Adopter`.

```yaml
burpsuite_extensions_bapp:
  - name: "ParamMiner"
    bapp_uuid: "17d2949a985c4b7ca092728dba871943"
    bapp_serial_version: "33"
    type: "java"
    use_ai: false
    loaded: true

burpsuite_extensions_external:
  - name: "CSTC"
    download_url: "https://github.com/usdAG/cstc/releases/download/v1.3.4/CSTC-1.3.4-jar-with-dependencies.jar"
    loaded: true
```

The extensions to install can be defined in the variables following variables:

- `burpsuite_extensions_bapp`: Burp App Store extensions.
- `burpsuite_extensions_external`: External extensions.

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - pluggero.burpsuite
```

## License

MIT / BSD

## Author Information

This role was created in 2025 by Robin Plugge.
