cmake_minimum_required(VERSION 2.8.10)
project(ortools-test C CXX)

set (PROJECT_CXX_FLAGS "-std=c++11")
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake")
set(CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} ${ORTOOLS_ROOT})
find_package(ortools REQUIRED)

include_directories(
    ${ORTOOLS_INCLUDE_DIRS}
)

# compiler flags
set (CMAKE_CXX_FLAGS "${PROJECT_CXX_FLAGS} ${CMAKE_CXX_FLAGS} -DUSE_GLOP -Wall -pedantic -g")

add_executable(test-app program.cc)
target_link_libraries(test-app ${ORTOOLS_LIBRARIES})
