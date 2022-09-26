cmake_minimum_required(VERSION 2.9)

project(app)

include_directories(${PROJECT_SOURCE_DIR}/include)
# subdirectories include via add_subdirectory()

## static or shared library example
add_library(applib ./src/fun.c)
# add_library(applib STATIC ./src/fun.c) # Builds an static library
# add_library(applib SHARED ./src/fun.c) # Builds an shared library

## macro example
# macro(set_my_variable _INPUT)
#   if("${_INPUT}" STREQUAL "Foo")
#     set(my_output_variable "foo")
#   else()
#     set(my_output_variable "bar")
#   endif()
# endmacro(set_my_variable)
# set_my_variable("Foo")
# message(STATUS ${my_output_variable})

## find package example
# set(CMAKE_MODULE_PATH "${CMAKE_MODULE_PATH} ${CMAKE_SOURCE_DIR}/cmake/modules")
# find_package(SDL2 REQUIRED)
# include_directories(${SDL2_INCLUDE_DIRS})

## pkg search example
include(FindPkgConfig)
pkg_search_module(SDL2 REQUIRED sdl2>=2.0.1)


## link example
add_executable(${PROJECT_NAME} ./src/main.c)
target_link_libraries(${PROJECT_NAME} applib ${SDL2_LIBRARIES})
