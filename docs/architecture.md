# Architecture

WallensteinVR splits rendering and XR setup into small Zig modules.

- `xr.zig` initializes OpenXR, manages sessions, and handles VR swapchains for stereo rendering.
- `vulkan/context.zig` creates the Vulkan instance and manages the overall Vulkan context.
- `vulkan/device.zig` handles physical device selection, queue family detection, and logical device creation.
- `main.zig` wires the pieces together.

This layout keeps the code base modular and easier to extend.

## OpenXR Session Management

The OpenXR Context (`xr.zig`) provides comprehensive VR session management with full swapchain and view support:

### Core Components
- **Session Management**: Creates and manages OpenXR sessions with Vulkan graphics binding
- **System Integration**: Handles system enumeration and properties for HMD devices
- **Reference Space**: Manages local reference space for tracking and rendering
- **Swapchain Management**: Complete multi-swapchain creation and management for stereo VR rendering
- **View Configuration**: Dynamic view creation and configuration for VR displays

### Swapchain Architecture
The `Swapchain` structure provides complete VR rendering target management:
- **Automatic Creation**: `createSwapchains()` function handles view configuration enumeration and swapchain creation
- **Multi-Eye Support**: Creates separate swapchains for each eye based on view configuration
- **Vulkan Integration**: Direct integration with Vulkan images (`XrSwapchainImageVulkanKHR`)
- **Optimal Resolution**: Uses recommended image dimensions from view configuration
- **Format Management**: Configures R8G8B8A8_SRGB format optimized for VR rendering
- **Usage Flags**: Sets appropriate usage flags for sampling and color attachment

### View Management
The `createViews()` function provides:
- **Dynamic View Creation**: Automatically creates views based on system configuration
- **Stereo Support**: Handles PRIMARY_STEREO view configuration for dual-eye rendering
- **Memory Efficiency**: Allocator-based view management with proper initialization
- **Type Safety**: Proper XR view type initialization for OpenXR compatibility

### Implementation Details
- **Error Handling**: Comprehensive error checking for all OpenXR operations
- **Resource Management**: Proper allocation and deallocation patterns
- **Configuration Queries**: Automatic enumeration of view configuration properties
- **Image Management**: Handles swapchain image enumeration and storage

## Vulkan Device Management

The Vulkan device management is handled in two main components:

### Physical Device Selection (`vulkan/device.zig`)
- Enumerates available physical devices
- Prioritizes discrete GPUs with geometry shader support
- Provides detailed logging of device selection process

### Queue Family Detection
- Safely detects graphics queue families with proper bounds checking
- Limits queue family enumeration to 16 families maximum for safety
- Uses improved logging for better debugging experience
- Implements proper type casting for queue family indices

### Logical Device Creation
- Creates logical device with selected graphics queue family
- Manages device queue creation and retrieval
- Handles proper resource cleanup through the deinit pattern
