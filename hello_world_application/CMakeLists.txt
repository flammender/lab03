cmake_minimum_required(VERSION 3.10)
project(hello_world_app CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
add_executable(hello_world hello_world.cpp)
target_link_libraries(hello_world PRIVATE formatter_ex solver)
