# Ansible Collection - voler88.workstation

Setup work environment in Linux OS.

## Description

A collection of software developments from the author's vision for the workstation.  
All the following theses are personal opinions.

### Roles

- **Window manager**: Sway

> - Flexible settings of windows and key bindings.
> - Beautiful and lightweight.

- **Terminal emulator**: Foot

> - Sway native.

- **Backup tools**: Syncthing

> - Decentralised, encrypted, continuous file synchronization.
> - Cross-platform.

### Roadmap

> - **IDE**: Neovim
> - **Email client**: Betterbird
> - **SIP client**: Linphone

### Variables

`USER` - remote Ansible user, i.e. for local install - current user.  
`HOME` - home directory of `USER`.

#### Window manager

| Variable        | Description                                    | Defaults                            |
| --------------- | ---------------------------------------------- | ----------------------------------- |
| wm_username     | Name of desktop user for autologin.            | `USER`                              |
| wm_autologin    | Enable autologin to desktop.                   | true                                |
| wm_dark_theme   | Enable dark theme by default for GTK+ windows. | true                                |
| wm_gtk3_config  | Path to GTK+ 3 settings file.                  | `HOME`/.config/gtk-3.0/settings.ini |
| wm_sway_dir     | Path to Sway directory with settings.          | `HOME`/.config/sway                 |
| wm_swaylock_dir | Path to Swaylock directory with settings.      | `HOME`/.config/swaylock             |
| wm_waybar_dir   | Path to Waybar directory with settings.        | `HOME`/.config/waybar               |

#### Terminal emulator

| Variable           | Description                                                         | Defaults                                      |
| ------------------ | ------------------------------------------------------------------- | --------------------------------------------- |
| term_foot_config   | Path to Foot settings file.                                         | `HOME`/.config/foot/foot.ini                  |
| term_term          | Value to set the environment variable TERM to.                      | xterm-256color                                |
| term_font_name     | Font name for text in terminal.                                     | SourceCodePro                                 |
| term_font_size     | Text size in terminal.                                              | 13                                            |
| term_base16_dir    | Path to directory with Base16 Tinted Theming for Foot.              | `HOME`/.config/foot/base16                    |
| term_base16_repo   | Base16 Tinted Theming for Foot git repository URL address.          | https://github.com/tinted-theming/base16-foot |
| term_base16_branch | Git branch name from Base16 Tinted Theming for Foot git repository. | main                                          |
| term_base16_theme  | Theme name from Base16 Tinted Theming for Foot.                     | zenburn                                       |

### Tags

| Tag                | Description                                                                         |
| ------------------ | ----------------------------------------------------------------------------------- |
| wm                 | Deploy only Window manager.                                                         |
| wm:cleanup         | Deploy only Window manager with cleanup Sway settings directories.                  |
| wm:configs         | Deploy only Window manager's settings files.                                        |
| wm:configs:cleanup | Deploy only Window manager's settings files with cleanup Sway settings directories. |
| wm:gtk             | Deploy only Window manager's GTK+ settings.                                         |
| term               | Deploy only Terminal emulator.                                                      |
| term:configs       | Deploy only Terminal emulator's settings files.                                     |

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

- You can provide variables via inventory file, vault file or from command line via --extra-vars.
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
