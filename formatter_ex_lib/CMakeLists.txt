cmake_minimum_required(VERSION 3.10)
project(formatter_ex)

set(formatter_DIR "${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib")
find_library(formatter_LIB
    NAMES formatter
    PATHS "${formatter_DIR}/build"
    NO_DEFAULT_PATH
    REQUIRED
)

add_library(formatter_ex STATIC
    formatter_ex.cpp
    formatter_ex.h
)

target_link_libraries(formatter_ex PRIVATE ${formatter_LIB})

target_include_directories(formatter_ex PRIVATE "${formatter_DIR}")
