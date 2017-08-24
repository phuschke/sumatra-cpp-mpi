project(ProjectName CXX)
cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} --coverage")

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/CMakeModules)

find_package(MPI REQUIRED)
include_directories(SYSTEM ${MPI_INCLUDE_PATH})

enable_testing()

# subdirectories
add_subdirectory(test)
add_subdirectory(examples)
