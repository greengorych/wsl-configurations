# wsl.conf - Default WSL per-distribution Configuration File

## Overview

This is a fully commented [`wsl.conf`](https://github.com/greengorych/wsl-configurations/blob/main/defaults/wsl.conf/wsl.conf) configuration file, designed to match the standard behavior of WSL instances, as if it were part of the default distribution installation. It provides detailed explanations for each section and parameter, including default values, available options, and dependencies, making it easier to understand and customize your configuration.

>[!NOTE]
>In this document, the term "instance" refers to an installed and running WSL distribution with its own filesystem and settings.

>[!IMPORTANT]
>All parameters in this file match the default WSL values, except for `<UserName>`. If you only update `<UserName>`, the instance will behave exactly like a standard WSL distribution with standard `wsl.conf` configuration.

## What is wsl.conf?

- `wsl.conf` is a configuration file for individual WSL instances.
- It allows you to manage settings such as:
  - System initialization (`systemd`).
  - Mounting Windows drives and configuring their behavior.
  - Network configuration (`hostname`, `hosts`, `resolv.conf`).
  - Timezone settings (`timezone`).
  - Interop between Windows and Linux.
  - The default Linux user.
  - And more.

>[!WARNING]
>Some parameters listed in `wsl.conf` are not documented officially. Additional undocumented parameters may also exist.

## Why Use wsl.conf?

- To understand the available configuration options and manage WSL instance behavior.
- To explicitly define settings rather than relying on hidden defaults.
- To minimize configuration changes and keep the system as close to the standard behavior as possible.

## How to Apply the Configuration?

To apply the configuration:

1. Modify the necessary parameters in the `wsl.conf` file.
2. Replace `<UserName>` with the desired Linux username.
3. Save the file at `/etc/wsl.conf` inside your WSL instance.

>[!TIP]
>Refer to the [**.cloud-init**](https://github.com/greengorych/wsl-configurations/tree/main/defaults/.cloud-init) example and its provided configuration file to automate `wsl.conf` creation.

## How to Apply Changes?

For the configuration changes to take effect, restart the instance:

```powershell
wsl -d <InstanceName> --shutdown
```

Then start the instance again:

```powershell
wsl -d <InstanceName>
```

## Related links

- [Advanced settings configuration in WSL](https://learn.microsoft.com/en-us/windows/wsl/wsl-config)
- [default.user-data – Default cloud-init Configuration File](https://github.com/greengorych/wsl-configurations/tree/main/defaults/.cloud-init)