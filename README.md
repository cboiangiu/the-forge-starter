# the-forge-starter

> This repo and [The-Forge.cmake](https://github.com/cboiangiu/The-Forge.cmake) are a work in progress.

> Currently trying to get this to work on a 2015 Macbook Pro using the Metal renderer.

> The goal is to have it work for macOS (`Metal`), windows (`D3D12`) and linux (`Vulkan`) first.

## Cloning

This project use [git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules) feature so you must clone the repo recursively
```bash
git clone --recursive https://github.com/cboiangiu/the-forge-starter.git the-forge-starter
```

## Prerequisites

Before attempting to build this project __all third party dependencies__ (`The-Forge`) must be __downloaded and installed__ (CMake now takes care of this with `ExternalProject_Add`). To achieve this `CMake` must be installed on your system (repo tested with CMake version `3.15`).

> Note: The libraries are self contained in the repo and are not installed to the system.

Please see the third-party [__README__](third-party/README.md) for full instructions on how to do this.

> Do __not__ proceed to __Build Instructions__ until you've done this.

## Build Instructions

Once all third party libraries have been downloaded and installed, follow these build instructions to compile the repo.

Shader compilation? Find a way. Then add them in `Resources/`.

> __Info:__ A `configure.bat` and `configure.sh` file are provided (mainly as an exmaple) to run the CMake configure commands. `Ninja` was chosen as the generator for these as it's consistent across _macOS_, _Linux_ and _Windows_, any generator should work though. There's also `configure-vs.bat` for generating a Visual Studio solution.

### Windows

- Run `./configure.bat` located in the root directory to generate the build files required for the project.
- Run `cmake --build build/debug` and/or `cmake --build build/release` to compile the project.
- Launch the application by running `build\debug\the-forge-starter.exe` or `build\release\the-forge-starter.exe`.

### macOS

- Run `./configure.sh` located in the root directory to generate the build files required for the project.
- Run `cmake --build build/debug` and/or `cmake --build build/release` to compile the project.
- Launch the application by running `./build/debug/the-forge-starter` or `./build/release/the-forge-starter`.

### Linux

- Run `./configure.sh` located in the root directory to generate the build files required for the project.
- Run `cmake --build build/debug` and/or `cmake --build build/release` to compile the project.
- Launch the application by running `./build/debug/the-forge-starter` or `./build/release/the-forge-starter`.
