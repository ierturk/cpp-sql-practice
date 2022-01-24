cmake_minimum_required(VERSION 3.21)

set(CMAKE_TOOLCHAIN_FILE ${CMAKE_CURRENT_SOURCE_DIR}/External/vcpkg/scripts/buildsystems/vcpkg.cmake
    CACHE STRING "Vcpkg toolchain file")

project(SQL-Cpp)

set(CMAKE_CXX_STANDARD 14)

find_package(unofficial-sqlite3 CONFIG REQUIRED)

add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE unofficial::sqlite3::sqlite3)

