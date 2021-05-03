# Ansible Role: rtl88 Themes
[![CI](https://github.com/skaary/ansible-role-arc_darkest_theme/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/skaary/ansible-role-arc_darkest_theme/actions?query=workflow%3Ci)

An Ansible Role that allows the download of [rtlewis88 themes](https://github.com/rtlewis88/) on Linux. The icons and desktop themes are installed system-wide (`/usr/share/icons` and `/usr/share/theme`).

## Requirements

None

## Dependencies

None

## Role variables

The variable `rtl_themes` has two entries called `directory` and `version`; `directory` denotes the directory name where the repository is cloned to (`/tmp/$directory`), `version` specifies the branch name of the wanted theme.

```yaml
rtl_themes:
  - directory: rtl88-crushed_icons
    version: CRUSHED-Icons-and-Folder
```

## Example Playbook

```yaml
- hosts: all
  rtl_themes:
  - directory: rtl88-crushed_icons
    version: CRUSHED-Icons-and-Folder
  - directory: rtl88-arc_darkest_complete
    version: Arc-Darkest-COLORS-Complete-Desktop
  - directory: rtl88-nord_black_frost
    version: Nord-Black-Frost
  roles:
    - rtl88_themes
```
