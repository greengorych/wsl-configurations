# Windows Subsystem for Linux (WSL) — Configuration Examples

## Overview

A curated set of configuration files and usage examples for Windows Subsystem for Linux (WSL).
This repository helps you customize, optimize, and automate the deployment of your WSL environment with:

- **.wslconfig** – a global configuration file for Windows Subsystem for Linux, which applies only to WSL 2 virtual machines.
- **wsl.conf** – a per-distribution configuration file used by both WSL 1 and WSL 2 virtual machines.
- **cloud-init** – a set of tools for automatically configuring virtual machines at first boot.
- **Ansible** – an automation tool used for configuration management, application deployment, and task automation across systems.

## Repository Structure

### Defaults

- [**.wslconfig**](https://github.com/greengorych/wsl-configurations/tree/main/defaults/.wslconfig) - a fully documented global configuration file for Windows Subsystem for Linux, applicable only to WSL 2 virtual machines. It describes all known parameters, their possible values, dependencies, and default settings.
- [**wsl.conf**](https://github.com/greengorych/wsl-configurations/tree/main/defaults/wsl.conf) - a fully commented per-distribution configuration file used by both WSL 1 and WSL 2 virtual machines. It describes all known parameters, their possible values, and default settings.

### cloud-init

> [!IMPORTANT]
> The examples in this section require WSL 1 or WSL 2 distributions that support initialization via cloud-init.

- [**cloud-init-wsl-conf**](https://github.com/greengorych/wsl-configurations/tree/main/cloud-init/cloud-init-wsl-conf) – a fully commented cloud-init configuration that generates and customizes `wsl.conf`, creates a user, and sets their password at first boot.
- [**cloud-init-ansible-venv**](https://github.com/greengorych/wsl-configurations/tree/main/cloud-init/cloud-init-ansible-venv) – a fully commented cloud-init configuration that sets up a Python virtual environment and installs Ansible and related tools.

### Ansible

- [**ansible-role-wsl-conf**](https://github.com/greengorych/ansible-role-wsl-conf) - Ansible role for generating or modifying `wsl.conf` for WSL 1 and WSL 2 distributions.
- [**ansible-role-wslconfig**](https://github.com/greengorych/ansible-role-wslconfig) - Ansible role for managing Windows Subsystem for Linux (WSL) global configuration file `.wslconfig`.

## How to Use

Usage information can be found in the instructions provided with each example.

## Contributing

Feel free to open issues, suggest improvements, or contribute new examples.

## License

MIT - free to use, modify, and share.
