# ваш_главный_каталог/CMakeLists.txt

cmake_minimum_required(VERSION 3.10)
project(YourMegaProject CXX) # Замените "YourMegaProject" на имя вашего проекта

# Устанавливаем требуемый стандарт C++ для всего проекта
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Добавляем подкаталоги. CMake автоматически найдет в них CMakeLists.txt и запустит их.
add_subdirectory(formatter_lib)
add_subdirectory(formatter_ex_lib)
add_subdirectory(solver_lib)
add_subdirectory(hello_world_application)

# Указываем, что исполняемый файл "hello_world" зависит от библиотек.
# Это гарантирует правильный порядок сборки.
add_dependencies(hello_world formatter_ex solver) # hello_world зависит от formatter_ex и solver

# Опционально: Устанавливаем целевые каталоги для исполняемых файлов и библиотек.
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
