This project is used for learning cmake. please ref to book "Learning cmake".

## how to use
``` 
mkdir build && cd build
cmake ..
make VERBOSE=1
``` 
## how to debug
add message(${MY_VARIABLE}) calls into CMakeLists.txt or *.cmake to debug variablesthat you want to inspect.

cmake -D CMAKE_FIND_DEBUG_MODE=ON ..