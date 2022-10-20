cmake_minimum_required(VERSION 3.19)

project(ASTC_CRASH LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(GLFW_BUILD_DOCS OFF CACHE BOOL "GLFW lib only")
set(GLFW_INSTALL OFF CACHE BOOL "GLFW lib only")
add_subdirectory(glfw)

find_package(Vulkan REQUIRED)

add_executable(main)
target_sources(main PRIVATE main.cpp)
target_link_libraries(main PRIVATE Vulkan::Vulkan glfw)
