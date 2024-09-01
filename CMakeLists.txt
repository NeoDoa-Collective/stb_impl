cmake_minimum_required(VERSION 3.26.4)

project(stb_impl)

add_library(stb_impl "stb.cpp")

find_package(Stb REQUIRED)
target_include_directories(stb_impl PUBLIC ${Stb_INCLUDE_DIR})

# Disable all warnings - STB is external library
if (MSVC)
    target_compile_options(stb_impl PRIVATE /W0)
elseif ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
    target_compile_options(stb_impl PRIVATE -w)
elseif ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang")
    target_compile_options(stb_impl PRIVATE -w)
endif()