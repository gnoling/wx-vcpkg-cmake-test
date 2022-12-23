# wx-vcpkg-cmake-test

This is a simple test / example of compiling the "minimal" WxWidgets example, using cmake and vcpkg.

## dependencies

A working build environment, cmake. On ubuntu, this is likely "apt install build-essential cmake". On windows, the default installation of Visual Studio Community Edition 2022 works out of the box.

Vcpkg is cloned as a submodule, and then it handles the WxWidgets and related dependencies. You do not need either before building this example.

## clone

    git clone --recurse-submodules https://github.com/gnoling/wx-vcpkg-cmake-test.git

## compile

If using Visual Studio, make sure to open a Developer Command Prompt for the following commands and not a regular console.

    cd wx-vcpkg-cmake-test
    cmake -B build .
    cmake --build build

## run

    Varies by platform, but you'll find the compiled executable under the build directory.

