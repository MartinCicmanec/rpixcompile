cmake_minimum_required (VERSION 3.10.1)

project(XCompile)
### https://cicero.xyz/v2/remark/github/scisoft/toolbox-talks/master/cmake-kung-fu.mkd/#1
### https://medium.com/@au42/the-useful-raspberrypi-cross-compile-guide-ea56054de187
### https://github.com/raspberrypi/tools

# The version number.
SET(PROJECT_VERSION_MAJOR 1)
SET(PROJECT_VERSION_MINOR 0)

# Set C++ compiler version
SET(CMAKE_CXX_STANDARD 14)
SET(CMAKE_CXX_STANDARD_REQUIRED ON)
SET(CMAKE_CXX_EXTENSIONS OFF)

SET(CMAKE_SYSTEM_NAME Linux)
SET(CMAKE_GENERATOR "GNU Makefiles")

# which compilers to use for C and C++
SET(tools /home/martin/git/tools)
SET(CMAKE_C_COMPILER ${tools}/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/bin/arm-linux-gnueabihf-gcc)
SET(CMAKE_CXX_COMPILER ${tools}/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/bin/arm-linux-gnueabihf-g++)

# Define the sysroot path for the RaspberryPi distribution in our tools folder 
SET(CMAKE_FIND_ROOT_PATH ${tools}/arm-bcm2708/arm-rpi-4.9.3-linux-gnueabihf/arm-linux-gnueabihf/sysroot/)

SET(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
SET(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
SET(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)
SET(CMAKE_FIND_ROOT_PATH_MODE_PACKAGE ONLY)

add_definitions(-Wall)

# Print all compile commands
SET(CMAKE_VERBOSE_MAKEFILE OFF)

include(ProcessorCount)
ProcessorCount(N)
message(STATUS "Number of available threads " ${N})

SET(EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR})

file(GLOB SOURCES "${CMAKE_SOURCE_DIR}/src/*.cpp")

add_executable(main ${SOURCES})

target_link_libraries(main PUBLIC
)

target_include_directories(main PUBLIC
    ${CMAKE_SOURCE_DIR}/include
)