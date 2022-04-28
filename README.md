# rust-arm-crosscompile
Docker used for cross-compiling rust programs for ARM/ARM64. Mainly used for RPI 3B

## Updates
Automatically updated every 30 days

## How to use
1. Add to lines to .cargo/config.toml
```
[target.armv7-unknown-linux-gnueabihf]
linker = "arm-linux-gnueabihf-gcc"
[target.aarch64-unknown-linux-gnu]
linker = "aarch64-linux-gnu-gcc"
```
2. docker run -v $PWD:/project -it skrcka/rust-arm-crosscompile
3. cargo build
    - cargo build --target armv7-unknown-linux-gnueabihf - for ARM
    - cargo build --target aarch64-unknown-linux-gnu - for ARM64
    - add --release to cargo build for optimized production build