cmake_minimum_required(VERSION 3.1)

project(shanten-number-calculator)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS_DEBUG "-O0 -Wall -g -DCHECK_HAND")
set(CMAKE_CXX_FLAGS_RELEASE "-O3 -Wall")

execute_process(COMMAND ${CMAKE_COMMAND} -E tar zxvf ${PROJECT_SOURCE_DIR}/index_dw.tar.gz)

option(THREE_PLAYER "Three player mode" off)

add_definitions(-DINDEX_FILE_PATH="${PROJECT_BINARY_DIR}")

if(THREE_PLAYER)
  add_definitions(-DTHREE_PLAYER)
endif()

add_executable(mkind2 mkind2.cpp judwin.cpp)
add_executable(sample sample.cpp calsht_dw.cpp)
