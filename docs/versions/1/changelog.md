# Changelog for 1.0.1

- Initial project skeleton and MIT license
- Added OpenXR and Vulkan wrappers
- Implemented OpenXR initialization and session creation
- Introduced modular `xr` and `vulkan` components
- Added Vulkan physical device selection
- Cleaned repository and improved `.gitignore`
- Expanded README with installation instructions and runtime links
- Added helper function `createPhysicalDevice` for Vulkan
- Introduced `logicalDevice.zig` to manage queue access
- Reworked Vulkan and XR modules for clarity and surface support
- Removed cached build artifacts from version control
- Added Nix flake for reproducible development shells
- Removed legacy C and C++ bindings in favor of pure Zig
- Improved XR-Vulkan integration and debug utilities
- Fixed several invalid pointer casts and cleanup warnings
