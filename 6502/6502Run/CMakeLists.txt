cmake_minimum_required(VERSION 3.17)
project(M6502Run)

set(CMAKE_CXX_STANDARD 14)

set(M6502_SOURCES "src/main_6502.cpp")

set(GLEW_H /usr/local/Cellar/glew/2.2.0_1/include/GL)
set(GLFW_H /usr/local/Cellar/glfw/3.3.2/include/GLFW)
include_directories(${GLEW_H} ${GLFW_H})

set(GLEW_LINK /usr/local/Cellar/glew/2.2.0_1/lib/libGLEW.2.2.dylib)
set(GLFW_LINK /usr/local/Cellar/glfw/3.3.2/lib/libglfw.3.dylib)
link_libraries(${OPENGL} ${GLEW_LINK} ${GLFW_LINK})

add_executable(M6502Run ${M6502_SOURCES})
add_dependencies(M6502Run M6502Lib)
target_link_libraries(M6502Run M6502Lib)

if (APPLE)
    target_link_libraries(M6502Run "-framework OpenGL")
    target_link_libraries(M6502Run "-framework GLUT")
endif ()