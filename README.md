# Ansible Role: rtl88 themes
[![CI](https://github.com/skaary/ansible-role-rtl88_themes/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/skaary/ansible-role-rtl88_themes/actions?query=workflow%3Ci)

An Ansible Role that allows the download of [rtlewis88 themes](https://github.com/rtlewis88/) on Linux. The icons and desktop themes are installed system-wide (`/usr/share/icons` and `/usr/share/theme`).

## Installation

Download the role directly from git by typing into your terminal:

```bash
ansible-galaxy install git+https://github.com:skaary/ansible-role-rtl88_themes.git
```

or

```bash
ansible-galaxy install git+https://github.com:skaary/ansible-role-rtl88_themes.git,,rtl88_themes
```

to change the installed role name from *ansible-role-rtl88_themes* to just  *rtl88_themes*.

Alternatively, install the role via a *requirements.yml* file, e.g. when installing multiple roles at once. See [ansible galaxy documentation](https://galaxy.ansible.com/docs/using/installing.html#installing-multiple-roles-from-a-file) for more information.

## Role variables

The variable `rtl_themes` has two entries called `directory` and `version`. The variable `directory` denotes the directory name where the repository is cloned to (`/tmp/$directory`) before the contents are moved to `/usr/share/icons` or `/usr/share/theme`. The variable `version` specifies the branch name of the wanted theme. For instance, to download the Arc-Darkest-Color theme the required git branch is [Arc-Darkest-Color](https://github.com/rtlewis88/rtl88-Themes/tree/Arc-Darkest-COLORS-Complete-Desktop).

## Example Playbook

```yaml
- hosts: all
  roles:
    - rtl88_themes
  rtl_themes:
  - directory: rtl88-crushed_icons
    version: CRUSHED-Icons-and-Folder
  - directory: rtl88-arc_darkest_complete
    version: Arc-Darkest-COLORS-Complete-Desktop
  - directory: rtl88-nord_black_frost
    version: Nord-Black-Frost
```

## Testing the role

### Vagrant

Vagrant can be used to test the role in order to graphically see it working in a virtual machine. Make sure Vagrant and VirtualBox are installed:

```bash
$ sudo apt install vagrant virtualbox
```

Use the following commands to run vagrant and boot up the virtual machine:

```bash
$ cd tests
$ vagrant up
```

Use `vagrant destroy` after you are done testing to delete the virtual machine. For more information about Vagrant and its commands, see the [Vagrant documentation](https://www.vagrantup.com/docs/cli).

### Molecule with Docker

Molecule can be used to test the role with a docker container. Make sure Molecule is installed:

```bash
$ python3 -m pip install --user "molecule[docker]"
```

Use the following commands to run Molecule in order to create the docker container and access the created container:
```bash
$ molecule converge && molecule login
```

For more information on how to use Molecule please consult the [Molecule documentation](https://molecule.readthedocs.io/en/latest/getting-started.html).

> Note: Python and Docker are required for the use of molecule. For more information, see [Molecule installation](https://molecule.readthedocs.io/en/latest/installation.html).

## License

MIT / BSD
