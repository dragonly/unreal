cmake_minimum_required(VERSION 3.7)
project(unreal)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/Modules/")

find_package(OpenGL REQUIRED)
include_directories(${OPENGL_INCLUDE_DIR})
set(LIBS ${LIBS} ${OPENGL_LIBRARIES})
message("OpenGL library path: ${OPENGL_LIBRARIES}")

find_package(GLFW REQUIRED)
include_directories(${GLFW_INCLUDE_DIR})
set(LIBS ${LIBS} ${GLFW_LIBRARIES})
message("GLFW library path: ${GLFW_LIBRARIES}")

include_directories(${CMAKE_SOURCE_DIR}/include)
set(HEADER_FILES include/gl.h)
set(SOURCE_FILES main.cpp)
add_executable(unreal ${SOURCE_FILES} ${HEADER_FILES})
target_link_libraries(unreal ${LIBS})