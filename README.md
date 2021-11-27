# Minimal Clap Host

This repo serves as an example to demonstrate how to create a host for CLAP plugins.

## Building on various platforms

### macOS

```shell
# Install dependencies
brew install qt6 pkgconfig rtaudio rtmidi

# Checkout the code
git clone --recurse-submodules https://github.com/free-audio/clap-host
cd clap-host

# Build
cmake --preset xcode-system
cmake --build builds/xcode-system --target clap-host --config Release

# Run
builds/xcode-system/host/Release/clap-host -p "<path-to-plugin>"
```

### Windows

Use the following command inside powershell:
```powershell
# Checkout the code
git clone --recurse-submodules https://github.com/free-audio/clap-host
cd clap-host

# Build
cmake --preset vs-vcpkg
cmake --build builds\vs-vcpkg --target clap-host --config Release

# Run
$env:QT_PLUGIN_PATH = "$pwd\builds\vs-vcpkg\vcpkg_installed\x64-windows\Qt6\plugins\"
builds\vs-vcpkg\host\Release\clap-host.exe -p "<path-to-plugin>"
```
