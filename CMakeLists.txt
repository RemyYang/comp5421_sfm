cmake_minimum_required(VERSION 3.2)
project(sfm)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_BUILD_TYPE Release CACHE STRING "Choose the type of build." FORCE)
set(SOURCE_FILES
lightweight_vector.hpp
mild.hpp
sparse_match.cpp
sparse_match.h
        cv_sfm.cpp
        cv_sfm.h
        frame.cpp
        frame.h
        main.cpp)

set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Wall")

find_package(OpenCV REQUIRED)

add_executable(sfm ${SOURCE_FILES})

include_directories(${OpenCV_INCLUDE_DIRS})

target_link_libraries(sfm ${OpenCV_LIBS} )
