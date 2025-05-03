cmake_minimum_required(VERSION 3.10)
project(hello_world)

set(formatter_ex_DIR "${CMAKE_CURRENT_SOURCE_DIR}/../../formatter_ex_lib")
find_library(formatter_ex_LIB
    NAMES formatter_ex
    PATHS "${formatter_ex_DIR}/build"
    NO_DEFAULT_PATH
    REQUIRED
)

include_directories("${formatter_ex_DIR}")

add_executable(hello_world main.cpp)

target_link_libraries(hello_world PRIVATE ${formatter_ex_LIB})
