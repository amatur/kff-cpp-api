cmake_minimum_required(VERSION 3.10)

# set the project name
project(KFF)
project(KFF VERSION 1.0)
configure_file(kff_io.hpp.in kff_io.hpp)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)
# set(CMAKE_BUILD_TYPE Debug)

include_directories(${CMAKE_BINARY_DIR})

set(CMAKE_CXX_FLAGS "-Wall -Ofast -g")

set(SRCS
  kff_io.cpp
  )

set(HEADERS
  kff_io.hpp
  )

include_directories(${CMAKE_CURRENT_BINARY_DIR})

# add the executable
add_executable(kff_example main.cpp ${SRCS})

add_library(kff ${SRCS})
target_include_directories(kff PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
