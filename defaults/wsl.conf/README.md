# wsl.conf - Default WSL per-distribution Configuration File

## Overview

This is a fully commented default **wsl.conf** file that replicates the behavior of individual WSL distributions as if it were the original configuration file shipped with the distro. It provides detailed explanations of each section and parameter, including default values, dependencies, and possible options, making it easy to modify only what you need.

## What is **wsl.conf**?

- A per-distribution configuration file for WSL.
- Controls various settings specific to a single WSL distribution, such as:
  - System initialization (**systemd**).
  - Mounting Windows drives and customizing drive behavior.
  - Network configurations (**resolv.conf**, **hosts**).
  - Interoperability between Windows and Linux.
  - Default user for the distribution.
  - And more.

## Why use this file?

- Fine-tune individual distribution settings without affecting the global configuration.
- Modify specific parameters for performance optimization, mount points, or network behavior.
- Understand and control the way WSL2 interacts with Windows, the file system, and other networked systems.
- Avoid unnecessary configuration complexity by tweaking only what you need.

## Where to place it?

The **wsl.conf** file must be placed inside the root directory of the distribution's file system at: **/etc/wsl.conf**

To modify this file, you can use your favorite text editor inside your WSL distro or you can use cloud-init from this default example - [**.cloud-init**](https://github.com/greengorych/wsl-temp/tree/main/defaults/.cloud-init).

After making changes to wsl.conf, the changes will take effect the next time the WSL distribution is started.

## Apply Changes

To apply changes made to wsl.conf, you need to restart your WSL distribution. You can do this by running:

```powershell
wsl -d <DistroName> --shutdown
```

Then start the distro again to see the effects.

## Default Behavior Summary

All values in this configuration reflect WSL2's default behavior. If you load this file without changing any settings, WSL2 will behave exactly as if no .wslconfig file was present.

## Related links

- [Advanced settings configuration in WSL](https://learn.microsoft.com/en-us/windows/wsl/wsl-config)
