cmake_minimum_required(VERSION 2.9)

project(hello_world)

include_directories(${PROJECT_SOURCE_DIR}/include)
# subdirectories include via add_subdirectory()
add_library(applib ./src/fun.c)
add_executable(app ./src/main.c)
target_link_libraries(app applib)
