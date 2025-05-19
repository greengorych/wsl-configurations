# default.user-data – Default cloud-init Configuration File

## Overview

This is a fully commented **cloud-init** **default.user-data** configuration file, tailored specifically for WSL (Windows Subsystem for Linux) distributions that support initialization through cloud-init. It automatically sets up user accounts, configures system behavior via default **wsl.conf**, and applies default permissions and settings.

## What is **default.user-data**?

**cloud-init** is a widely used tool in cloud environments to automate the initialization and configuration of virtual machines. WSL now supports **cloud-init**, allowing preconfiguration of WSL distributions on first boot. The **default.user-data** file provides instructions to cloud-init on how to configure the WSL environment.

This includes:
- User creation
- User password creation
- Grant sudo permissions
- Base configuration via default **`/etc/wsl.conf`**

## Why use this file?

- Create and configure a default Linux user
- Grant sudo access for that user
- Preconfigure WSL system settings via **`/etc/wsl.conf`**
- Ensure consistent and repeatable WSL environments
- Automate custom WSL setup for diferent environments

## Where to place it?

The **.cloud-init** folder does not exist by default at: **`C:\Users\<UserName>\`** — you must create it manually.

For per-instance configuration:

For creation a specific instance cloud-init configuration file must be located at **`C:\Users\<UserName>\.cloud-init\<InstanceName>.user-data`** and has a name **`<InstanceName>.user-data`**.

For default configuration:

- For creation a common for all instances cloud-init configuration file must be located at **`C:\Users\<UserName>\.cloud-init\default.user-data`** and has a name **default.user-data**.

Replace **`<UserName>`** and **`<Password Hash>`** in the configuration with your desired username and password hash.

### How to generate a password hash?

To set a secure password for the Linux user in cloud-init, you need to provide a hashed password.
Use this command in Linux or WSL to generate a password hash using SHA-512:

```bash
openssl passwd -6
```

Copy the output and paste it in place of **`<Password Hash>`** in your configuration file.

### Apply Changes

The cloud-init configuration is applied automatically the first time a WSL distribution is started. If you've updated the file and want to reapply changes, you must shut down the WSL instance and delete the current one before recreating it.

To apply wsl.conf changes or restart cloud-init-enabled distros:

```powershell
wsl -d <DistroName> --shutdown
```

Then start the distro again to see the effects.

### How to verify cloud-init ran?

To view the status of cloud-init use this command:

```bash
cloud-init status
```

Or this command that waiting on cloud-init to complete:

```bash
cloud-init status --wait
```

If cloud-init worked whithout error you will see message: `status: done`.
If you will see message: `status: error`, you need find the reason that caused the error.

### Apply Changes

To apply changes made to cloud-init, you need to restart your WSL distribution. You can do this by running:

```powershell
wsl -d <DistroName> --shutdown
```

### How to verify cloud-init ran?

You can check the current status with:

```bash
cloud-init status
```

Or wait for it to complete:

```bash
cloud-init status --wait
```

Expected output when everything works:

```
status: done
```

If there’s an issue:

```
status: error
```

### How to debug errors?

To see detailed status and stages:

```bash
cloud-init status --long
```

To view the cloud-init output log:

```bash
sudo cat /var/log/cloud-init-output.log
```

This log will show errors and help you troubleshoot configuration issues.

## Related links

- [Using WSL with cloud-init](https://docs.cloud-init.io/en/latest/howto/launch_wsl.html)
- [cloud-init WSL](https://cloudinit.readthedocs.io/en/latest/reference/datasources/wsl.html)
- [Automatic setup of Ubuntu on WSL with cloud-init](https://documentation.ubuntu.com/wsl/en/stable/howto/cloud-init/)