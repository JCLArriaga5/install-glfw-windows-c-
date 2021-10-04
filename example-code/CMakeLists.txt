cmake_minimum_required(VERSION 3.10)

project(CreatingWindow)

set(CMAKE_PREFIX_PATH "C:/Program Files (x86)/GLFW/lib/cmake/glfw3")

add_executable(example-code src/main.cpp)

include_directories("C:/Program Files (x86)/GLFW/include/GLFW/")

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)
target_link_libraries(example-code opengl32 glfw)
