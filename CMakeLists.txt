cmake_minimum_required(VERSION 3.26.4)

project(stb_impl)

add_library(stb_impl "stb.cpp")

find_package(Stb REQUIRED)
target_include_directories(stb_impl PUBLIC ${Stb_INCLUDE_DIR})