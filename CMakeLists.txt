cmake_minimum_required(VERSION 3.10)

# Set the project name and version
project(opengl_final VERSION 1.0)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_MAKE_PROGRAM mingw32-make)

set(LIB_DIR deps)

# Add an executable
file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS src/*.cpp src/**/*.cpp)
add_executable(opengl_final ${SOURCES})


#Includes
target_include_directories(opengl_final PRIVATE include)

# Find and ADD GLFW (prebuilt)
# find_library(GLFW libglfw3 "${PROJECT_SOURCE_DIR}/deps/glfw")
# target_link_libraries(opengl_final PRIVATE ${GLFW})



# Find and ADD GLFW (from source)

# Add GLFW as a subdirectory
add_subdirectory("./libs/glfw")
add_subdirectory("./libs/glad")

# Include GLFW headers
target_include_directories(opengl_final PRIVATE "./libs/glfw/include")
target_include_directories(opengl_final PRIVATE "./libs/glad/include")


# Link GLFW library to your executable
target_link_libraries(opengl_final PRIVATE glfw glad opengl32)

