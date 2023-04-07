cmake_minimum_required(VERSION 3.10)

# Set the project name and version
project(glad VERSION 1.0)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_MAKE_PROGRAM mingw32-make)

file(GLOB SOURCES "glad.c")
include_directories("include")
add_library(glad STATIC ${SOURCES})