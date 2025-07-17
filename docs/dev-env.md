# Development Environment

This project ships a Nix flake for a reproducible dev setup.

```sh
nix develop
```

The environment provides the Zig compiler, Vulkan SDK, and OpenXR headers. After entering the shell, build and test as usual:

```sh
zig build
zig build test
```

