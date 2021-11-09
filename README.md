# Minimal Clap Host

This repo serves as an example to demonstrate how to create a host for CLAP plugins.

## Building on various platforms

### macOS

To build the example host on macOS you need a few extra libraries, qt6, boost, portmidi and portaudio.
These are all available by homebrew and the CMake setup will find them assuming a standard
(/usr/local) homebrew setup. Before your first build do

```shell
brew install qt6
brew install boost
brew install portaudio
brew install portmidi
brew install pkgconfig
```

### Windows

Use the following command inside powershell:
```powershell
# Checkout the code
git clone --recurse-submodules https://github.com/free-audio/clap-host
cd clap-host

# Build the host
cmake --preset vs-vcpkg
cmake --build builds\vs-vcpkg --target clap-host --config Release

# Run the host
$env:QT_PLUGIN_PATH = "$pwd\builds\vs-vcpkg\vcpkg_installed\x64-windows\Qt6\plugins\"
builds\vs-vcpkg\host\Release\clap-host.exe -p "<path-to-plugin>"
```
