# Ansible Role: Arc_Darkest_Theme
[![CI](https://github.com/skaary/ansible-role-arc_darkest_theme/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/skaary/ansible-role-arc_darkest_theme/actions?query=workflow%3Ci)

An Ansible Role that installs the theme [Arc Darkest Theme](https://github.com/rtlewis88/) on Linux.

## Requirements

None

## Dependencies

None

## Role variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
lxappearance: true
```

[Lxappearance](http://wiki.lxde.org/en/LXAppearance) is a style configuration tool for GTK 2 and GTK 3 and can be optionally installed to make setting the theme and icons easier; the values for `lxappearance` can be either true or false.

## Example Playbook

```yaml
- hosts: all
  roles:
    - skaary.arc_darkest_theme
```
