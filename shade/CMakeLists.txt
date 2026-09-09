cmake_minimum_required(VERSION 3.20)

project(shade LANGUAGES CXX)

add_library(shade INTERFACE)

target_include_directories(shade INTERFACE
    "${CMAKE_CURRENT_SOURCE_DIR}/.."
)

target_compile_features(shade INTERFACE cxx_std_23)