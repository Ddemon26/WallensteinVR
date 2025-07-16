# WallensteinVR

A modular OpenXR/Vulkan VR application built with Zig, featuring robust device management and graphics queue handling.

## Features

- **Complete OpenXR Integration**: Full session management with swapchain support for VR rendering
- **Robust Vulkan Device Selection**: Automatically selects the best available discrete GPU with geometry shader support
- **Safe Queue Family Detection**: Implements bounds-checked queue family enumeration with proper error handling
- **Modular Architecture**: Clean separation between OpenXR session management and Vulkan rendering context
- **VR Swapchain Management**: Handles multiple swapchains with Vulkan image integration for stereo rendering
- **Comprehensive Logging**: Detailed debug output for device selection and queue family detection

## Installation

### Windows 🪟

```sh
Idk, use linux tbh
```

### Linux 🐧

#### Debian/Ubuntu

```sh
sudo apt update
sudo apt install libopenxr-loader1
sudo apt install libopenxr-dev
```

#### Arch

```sh
sudo pacman -S openxr
```

NOTE: might require the vulkan SDK

### Runtimes

##### Monado — _Recommended_

[![Monado Repo](https://img.shields.io/badge/Monado-GitHub-black?style=flat&logo=github)](https://github.com/mateosss/monado)

`rm /tmp/monado_comp_ipc; monado-service`

##### Steam VR

[<img src="https://upload.wikimedia.org/wikipedia/commons/8/83/Steam_icon_logo.svg" width="20"/> Steam VR](https://store.steampowered.com/app/250820/SteamVR/)
