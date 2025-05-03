cmake_minimum_required(VERSION 3.10)
project(solver)

set(formatter_ex_DIR "${CMAKE_CURRENT_SOURCE_DIR}/../../formatter_ex_lib")
find_library(formatter_ex_LIB
    NAMES formatter_ex
    PATHS "${formatter_ex_DIR}/build"
    NO_DEFAULT_PATH
    REQUIRED
)
include_directories("${formatter_ex_DIR}")

set(solver_lib_DIR "${CMAKE_CURRENT_SOURCE_DIR}/../../solver_lib")
find_library(solver_lib_LIB
    NAMES solver_lib
    PATHS "${solver_lib_DIR}/build"
    NO_DEFAULT_PATH
    REQUIRED
)
include_directories("${solver_lib_DIR}")

add_executable(solver main.cpp)

target_link_libraries(solver PRIVATE ${formatter_ex_LIB} ${solver_lib_LIB})
