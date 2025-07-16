# Architecture

WallensteinVR splits rendering and XR setup into small Zig modules.

- `xr.zig` initializes OpenXR and manages the session.
- `vulkan/context.zig` creates the Vulkan instance and selects a physical device.
- `logicalDevice.zig` builds the logical device and exposes the graphics queue.
- `vulkan/chef.zig` contains helpers like `createPhysicalDevice`.
- `main.zig` wires the pieces together.

This layout keeps the code base modular and easier to extend.
