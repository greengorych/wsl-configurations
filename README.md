# Windows Subsystem for Linux (WSL) — Configuration Examples

## Overview

A curated set of configuration files and usage examples for Windows Subsystem for Linux (WSL).
This repository helps you customize, optimize and automate deployment your WSL environment with:

- **.wslconfig** - global configuration file for the WSL2 virtual michines.
- **wsl.conf** - per-distribution configuration file.
- **cloud-init** - a set of tools for automatically configuring virtual machines when they are first launched.

## Repository Structure

### Defaults

- [**.wslconfig**](https://github.com/greengorych/wsl-configurations/tree/main/defaults/.wslconfig) - a fully commented default configuration file that replicates the behavior of WSL2 as if no configuration file were present.
- [**wsl.conf**](https://github.com/greengorych/wsl-configurations/tree/main/defaults/wsl.conf) - a fully commented default configuration file that replicates the behavior of individual WSL distributions as if it were the original configuration file shipped with the distro.
- [**cloud-init**](https://github.com/greengorych/wsl-configurations/tree/main/defaults/.cloud-init) - a fully commented cloud-init **default.user-data** configuration file, tailored specifically for WSL (Windows Subsystem for Linux) distributions that support initialization through cloud-init.

### Examples

- [**ansible-venv**](https://github.com/greengorych/wsl-configurations/tree/main/examples/ansible-venv) - Creating a Python Virtual Environment with Ansible Tools.

## How to Use

You can find usage information in the instructions provided with each example.

## Contributing

Feel free to open issues, suggestions, or contribute improvements or new examples.

## License

MIT - free to use, modify, and share.
