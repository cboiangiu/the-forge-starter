cmake_minimum_required(VERSION 3.15)

project(third-party)

include(ExternalProject)

get_property(isMultiConfig GLOBAL PROPERTY GENERATOR_IS_MULTI_CONFIG)
if (NOT isMultiConfig)
    if(NOT CMAKE_BUILD_TYPE)
        set(CMAKE_BUILD_TYPE Debug CACHE STRING "" FORCE)
    endif()
    set(build_type_dir ${CMAKE_BUILD_TYPE})
    set(build_type_arg -DCMAKE_BUILD_TYPE=$<CONFIG>)
endif()

ExternalProject_Add(
    The-Forge
    BINARY_DIR ${CMAKE_CURRENT_BINARY_DIR}/The-Forge/build/${build_type_dir}
    INSTALL_DIR ${CMAKE_CURRENT_BINARY_DIR}
    SOURCE_DIR The-Forge.cmake
    CMAKE_ARGS ${build_type_arg}
               -D CMAKE_INSTALL_PREFIX=<INSTALL_DIR>
               -D D3D12=OFF
               -D METAL=ON
               -D VULKAN=OFF
               -D IOS=OFF
               -D ANDROID=OFF)
