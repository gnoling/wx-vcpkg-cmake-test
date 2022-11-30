cmake_minimum_required(VERSION 3.21.1)

option(ENABLE_VCPKG "Enable the vcpkg package manager" ON)
if (ENABLE_VCPKG)
	file(MAKE_DIRECTORY "${CMAKE_CURRENT_LIST_DIR}/dependencies/vcpkg_overlay_ports")
	set(VCPKG_OVERLAY_PORTS "${CMAKE_CURRENT_LIST_DIR}/dependencies/vcpkg_overlay_ports")
	set(CMAKE_TOOLCHAIN_FILE "${CMAKE_CURRENT_SOURCE_DIR}/dependencies/vcpkg/scripts/buildsystems/vcpkg.cmake" CACHE STRING "Vcpkg toolchain file")
	set(CMAKE_FIND_PACKAGE_PREFER_CONFIG TRUE)
	if (WIN32)
		set(VCPKG_TARGET_TRIPLET "x64-windows-static" CACHE STRING "")
	endif()
endif()

project(minimal)

set(wxWidgets_USE_UNICODE On)
set(wxWidgets_USE_UNIVERSAL On)

find_package(wxWidgets REQUIRED COMPONENTS base core xrc)

if(wxWidgets_FOUND)
  set(SRCS minimal.cpp)
  add_executable(minimal ${SRCS})
  target_link_libraries(minimal PRIVATE wx::base wx::core wx::xrc)
endif()

install(TARGETS minimal DESTINATION bin)

