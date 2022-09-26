cmake_minimum_required(VERSION 2.9)

project(hello_world)

include_directories(${PROJECT_SOURCE_DIR})

add_executable(app main.c fun.c)
