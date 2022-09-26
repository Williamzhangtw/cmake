cmake_minimum_required(VERSION 2.9)

project(hello_world)

include_directories(${PROJECT_SOURCE_DIR}/include)
# subdirectories include via add_subdirectory()
add_library(applib ./src/fun.c)
# add_library(applib STATIC ./src/fun.c) # Builds an static library
# add_library(applib SHARED ./src/fun.c) # Builds an shared library
macro(set_custom_variable _OUT_VAR)
  set(${_OUT_VAR} "Foo")
endmacro(set_custom_variable)
set_custom_variable(my_foo)
message(STATUS ${my_foo})

add_executable(app ./src/main.c)
target_link_libraries(app applib)
