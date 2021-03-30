cmake_minimum_required(VERSION 3.17)
project(M6502Run)

set(CMAKE_CXX_STANDARD 14)

set(M6502_SOURCES
        "src/main_6502.cpp")

add_executable(M6502Run ${M6502_SOURCES})
add_dependencies( M6502Run M6502Lib )
target_link_libraries(M6502Run M6502Lib)