cmake_minimum_required(VERSION 3.16)
project(Arsenic)

set(CMAKE_CXX_STANDARD 14)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

set(GLFW_INCLUDE /usr/local/include)
set(GLEW_INCLUDE /usr/include)
set(INCLUDE_DIRECTORIES ${GLFW_INCLUDE} ${GLEW_INCLUDE})

add_subdirectory(deps/glfw)
add_subdirectory(deps/glew-2.2.0/build/cmake)

include_directories(${INCLUDE_DIRECTORIES})
set(SOURCES main.cpp ${GLFW_INCLUDE}/GLFW/glfw3.h ${GLEW_INCLUDE}/GL/glew.h)
add_executable(Arsenic ${SOURCES})
target_link_libraries(Arsenic glfw)
target_link_libraries(Arsenic glew_s)
