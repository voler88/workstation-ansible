# Ansible Collection - voler88.workstation

Setup work environment in Linux OS.

## Description

A collection of software developments from the author's vision for the
workstation.  
All the following theses are personal opinions.

### Roles

- [**Window manager**](./roles/wm/defaults/main.yml): Sway

> - Flexible settings of windows and key bindings.
> - Beautiful and lightweight.

- [**Terminal emulator**](./roles/term/defaults/main.yml): Foot

> - Sway native.

- [**Backup tools**](./roles/backup/defaults/main.yml): Syncthing

> - Decentralised, encrypted, continuous file synchronization.
> - Cross-platform.

- [**IDE**](./roles/ide/defaults/main.yml): Neovim - LazyVim

> - Like Vim, but better.
> - Has many plugins and large community.
> - Works in the console.

### Roadmap

> - **Email client**: Betterbird
> - **SIP client**: Linphone

### Tags
<!-- markdownlint-disable MD013 -->

| Tag                 | Description                                                                         |
| ------------------- | ----------------------------------------------------------------------------------- |
| wm                  | Deploy only Window manager.                                                         |
| wm:cleanup          | Deploy only Window manager with cleanup Sway settings directories.                  |
| wm:configs          | Deploy only Window manager's settings files.                                        |
| wm:configs:cleanup  | Deploy only Window manager's settings files with cleanup Sway settings directories. |
| wm:fonts            | Deploy only Window manager's Nerd Fonts.                                            |
| wm:gtk              | Deploy only Window manager's GTK+ settings.                                         |
| term                | Deploy only Terminal emulator.                                                      |
| term:configs        | Deploy only Terminal emulator's settings files.                                     |
| backup              | Deploy only Backup tools.                                                           |
| ide                 | Deploy only IDE.                                                                    |
| ide:cleanup         | Deploy only IDE with cleanup Nvim settings directories.                             |
| ide:configs         | Deploy only IDE settings files.                                                     |
| ide:configs:cleanup | Deploy only IDE settings files with cleanup Nvim settings directories.              |

<!-- markdownlint-enable MD013 -->
## How to use collection

### Requirements

- Running on Fedora Atomic Sway 40

### Installation

1. Install Ansible.
2. Clone repo to default Ansible collections path as `voler88/workstation`:

```bash
git clone https://github.com/voler88/workstation-ansible.git "$HOME/.ansible/collections/ansible_collections/voler88/workstation"
```

### Start PLAY

Optional:

- You can provide variables via inventory file, vault file or from command line
  via --extra-vars.
- You can combine multiple tags, separated by commas, to run only certain tasks.

```bash
# (Optional) Suppress localhost warning.
export ANSIBLE_LOCALHOST_WARNING=False

# Deploy all roles.
ansible-playbook voler88.workstation.main

# Or deploy specific roles only.
ansible-playbook voler88.workstation.main --tags wm,term
```

## Release notes

See the [changelog](CHANGELOG.md) file.

## Licensing

See the [license](LICENSE) file.

## Author information

[![voler88](https://img.shields.io/badge/voler88-black?style=social&logo=github)](https://github.com/voler88)
