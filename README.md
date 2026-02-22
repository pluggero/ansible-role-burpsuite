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
# Unified list (backward compatible)
burpsuite_extensions_bapp: []

# Edition-specific lists (auto-merged based on burpsuite_edition)
burpsuite_extensions_bapp_community: []
burpsuite_extensions_bapp_pro: []

burpsuite_extensions_external: []
```

BApp extensions can be configured using:
- `burpsuite_extensions_bapp` - Unified list (takes precedence if set)
- `burpsuite_extensions_bapp_community` + `burpsuite_extensions_bapp_pro` - Edition-specific (auto-merged: community-only for community edition, both for pro edition)

External extensions: `burpsuite_extensions_external`

```yaml
burpsuite_eula_accepted: false
burpsuite_portswigger_analytics_enabled: false
burpsuite_pro_license: []  # List of license strings (renders as license1, license2, etc.)
burpsuite_additional_prefs: []  # Custom Java preferences: [{key: "...", value: "..."}]
```

Java preferences configuration.

```yaml
burpsuite_collaborator_type: "none"  # default, none, or private
burpsuite_collaborator_location: ""
burpsuite_collaborator_polling_location: ""
burpsuite_collaborator_poll_over_unencrypted_http: false
```

Collaborator server configuration. When using `private`, both location fields are required.

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
