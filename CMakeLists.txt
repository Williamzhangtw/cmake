cmake_minimum_required(VERSION 2.9)

project(hello_world)

include_directories(${PROJECT_SOURCE_DIR}/include)
# subdirectories include via add_subdirectory()
add_library(applib ./src/fun.c)
# add_library(applib STATIC ./src/fun.c) # Builds an static library
# add_library(applib SHARED ./src/fun.c) # Builds an shared library
add_executable(app ./src/main.c)
target_link_libraries(app applib)
