# API Reference

This page documents the main Zig modules and their exported functions.

## xr.zig

`Context` manages the OpenXR instance and session.

- **init** – creates the instance, enables requested extensions and layers, and opens a session.
- **deinit** – destroys the debug messenger, instance, and reference space.
- **getVulkanExtensions** – returns the Vulkan instance extensions required by OpenXR.
- **getXRFunction** – resolves an OpenXR function pointer safely.
- **createDebugMessenger** – installs a debug messenger that logs XR warnings and errors.
- **validateExtensions** – checks that requested OpenXR extensions exist.
- **validateLayers** – checks that requested API layers exist.

## vulkan/context.zig

`Context` wraps the Vulkan instance and device.

- **init** – creates the instance and selects a device.
- **deinit** – destroys the instance when finished.
- **createInstance** – internal helper that enables validation and required extensions.
- **debugCallback** – receives messages from Vulkan validation layers.

## vulkan/device.zig

`Device` represents the Vulkan physical and logical device pair.

- **init** – selects a GPU and creates a logical device with a graphics queue.
- **deinit** – frees the logical device.
- **selectPhysical** – chooses the first discrete GPU supporting geometry shaders.
- **createLogicalDevice** – builds the logical device and retrieves its graphics queue.
- **findQueueFamilies** – helper to locate the graphics queue family.

## main.zig

The `main` function wires everything together. It sets up required extensions and layers,
initializes `xr.Context`, and will later create a Vulkan context.

## c.zig

`check` converts C return codes into Zig errors. `wrapXR` maps every OpenXR error code
into a descriptive Zig error.
