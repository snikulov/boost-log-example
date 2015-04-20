cmake_minimum_required(VERSION 2.8)

project(boost_log CXX)

# we will use static libs
set(Boost_USE_STATIC_LIBS ON)

# Boost::log required Boost version >= 1.54.0 
find_package(Boost 1.54.0 REQUIRED COMPONENTS log)

include_directories(${Boost_INCLUDE_DIRS})
link_directories(${Boost_LIBRARY_DIRS})

set(SRC_FILES
    src/main.cpp)

add_executable(boost_log ${SRC_FILES})
target_link_libraries(boost_log ${Boost_LIBRARIES})
