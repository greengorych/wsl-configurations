# .wslconfig – Default WSL2 Configuration File

## Overview

This is a fully commented default **.wslconfig** file that replicates the behavior of WSL2 as if no configuration file were present. It provides detailed explanations of each section and parameter, including default values, dependencies, and possible options, making it easy to modify only what you need.

## What is **.wslconfig**?

- A global configuration file for WSL2 distributions.
- Has no effect on WSL1 distributions.
- Allows customization of:
  - Kernel, its modules and parametres
  - CPU and memory usage
  - Virtual machine disk size for new instances
  - Swap file size and its location
  - Networking and DNS settings
  - Proxy and firewall usage
  - Port forwarding
  - And more

## Why use this file?

- Use it as a baseline for customizing WSL2 to fit your needs.
- See all supported parameters along with their meanings and explanations.
- Understand dependencies between settings.
- Change only what you need while keeping everything else at default.

## Where to place it?

The **.wslconfig** file does not exist by default — you must create it manually.

It must be located at: **`C:\Users\<UserName>\.wslconfig`**

You can copy the content of the [**.wslconfig**](.wslconfig) file into a new file created at the path above, or simply copy the provided file into your user profile directory.

Changes will take effect the next time WSL2 starts.

## Apply Changes

After editing **.wslconfig**, apply the changes by shutting down WSL2:

```powershell
wsl --shutdown
```
Then start the distro again to see the effects.

## Default Behavior Summary

All values in this configuration reflect WSL2's default behavior. If you load this file without changing any settings, WSL2 will behave exactly as if no .wslconfig file was present.

## Related links

- [Advanced settings configuration in WSL](https://learn.microsoft.com/en-us/windows/wsl/wsl-config)
