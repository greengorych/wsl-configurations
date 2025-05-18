### Creating a Python Virtual Environment with Ansible Tools

## Overview

 This `cloud-init` configuration extends the [`default.user-data`](https://github.com/greengorych/wsl-configurations/tree/main/cloud-init/ansible-venv) by adding a Python virtual environment and installing key Ansible development tools: `ansible`, `ansible-lint`, and `molecule`.

## What are **ansible**, **ansible-lint** and **molecule**?

- **ansible** – A powerful automation tool used for configuration management, application deployment, and task automation.
- **ansible-lint** – A command-line tool that checks Ansible playbooks for best practices and common errors.
- **molecule** – A testing framework for developing and verifying Ansible roles using various drivers (e.g., `Docker`, `Vagrant`).

## Why use Python virtual environment for Ansible?

Using a virtual environment:
- Keeps your system `Python` clean and avoids conflicts with other tools
- Allows you to pin specific versions of Ansible and dependencies
- Makes it easier to upgrade, downgrade, or test different versions
- Improves reproducibility across environments

## How to apply this configuration?

Follow these steps:

1. Create folder `C:\Users\<UserName>\.cloud-init\` if it doesn't exist.
2. Rename `default.user-data` to `<InstanceName>.user-data` (where `<InstanceName>` is the name of your WSL distribution, e.g., `Ubuntu`, `Debian`) if you want to target a specific instance.
3. Place the resulting configuration at: `C:\Users\<UserName>\.cloud-init\`
4. Modify the `wsl.conf` section if you want to change WSL behavior.
5. Replace `<UserName>` with your desired Linux username.
6. Generate a password hash with the command below and replace `<Password Hash>`:

```bash
openssl passwd -6
```

## Apply Changes

The cloud-init configuration is applied automatically the first time a WSL distribution is started. If you've updated the file and want to reapply changes, you must shut down the WSL instance and recreate it to apply the updated configuration.  

Note: Recreating the instance will remove any data unless backed up.

To apply the changes, launch the distribution:

```powershell
wsl -d <InstanceName>
```

## How to verify cloud-init ran?

To view the status of cloud-init use this command:

```bash
cloud-init status
```

Or this command that waits for cloud-init to complete:

```bash
cloud-init status --wait
```

If `cloud-init` completes successfully, you will see:

> status: done

If there was an issue, you will see the cause:

> status: error

## How to debug errors?

To see detailed status and stages:

```bash
cloud-init status --long
```

To view the cloud-init output log:

```bash
sudo cat /var/log/cloud-init-output.log
```

This log will show errors and help you troubleshoot configuration issues.

## Reapply Changes

To apply changes made to cloud-init, you need to restart your WSL distribution. You can do this by running:

```powershell
wsl -d <InstanceName> --shutdown
```

and then:

```powershell
wsl -d <InstanceName>
```

## How to use the virtual environment?

To activate the virtual environment:

```bash
source ~/ansible-venv/bin/activate
```

To deactivate it:

```bash
deactivate
```

## How to update packages in the virtual environment?

1. Activate the virtual environment:

```bash
source ~/ansible-venv/bin/activate
```

2. List outdated packages:

```bash
pip list --outdated
```

3. Upgrade specific packages:

```bash
pip install --upgrade <Package1> <Package2>
```

## What to do if a package upgrade breaks Ansible?

Sometimes updating dependencies (e.g., `resolvelib`) can cause version conflicts:

Example of an incompatible upgrade:

```bash
pip install --upgrade resolvelib
```
You might see:

> ansible-core 2.18.5 requires resolvelib<1.1.0,>=0.5.3, but you have resolvelib 1.1.0 which is incompatible.

To fix this, reinstall the correct version:

```bash
pip install "resolvelib<1.1.0,>=0.5.3"
```

## Related links

- [wsl.conf - Default WSL per-distribution Configuration File](https://github.com/greengorych/wsl-configurations/tree/main/defaults/wsl.conf)
- [default.user-data – Default cloud-init Configuration File](https://github.com/greengorych/wsl-configurations/tree/main/cloud-init/wsl-conf)