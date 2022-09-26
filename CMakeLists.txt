cmake_minimum_required(VERSION 2.9)

project(hello_world)

include_directories(${PROJECT_SOURCE_DIR})
add_library(applib fun.c)
add_executable(app main.c)
target_link_libraries(app applib)
