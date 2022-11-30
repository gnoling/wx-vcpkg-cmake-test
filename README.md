# wx-vcpkg-cmake-test

This is a simple test / example of compiling the "minimal" WxWidgets example, using cmake and vcpkg.

## dependencies

A working build environment, cmake.

## clone

    git clone --recurse-submodules https://github.com/gnoling/wx-vcpkg-cmake-test.git

## build

The below use Makefile. You could also generate, say, Ninja, by doing `cmake -GNinja ..` at the cmake step and then using `ninja` to compile.

    cd wx-vcpkg-cmake-test
    mkdir build
    cd build
    cmake ..
    make

## run

    ./minimal
