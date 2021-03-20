cmake_minimum_required(VERSION 3.4.0)

project(myboostapp)

include(${CMAKE_ROOT}/Modules/ExternalProject.cmake)

# SET ( CMAKE_BUILD_TYPE Debug )
# SET(CMAKE_CXX_FLAGS_RELWITHDEBINFO "-O2 -g")
SET(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS_RELWITHDEBINFO})


SET ( CMAKE_VERBOSE_MAKEFILE true )
set (CMAKE_EXPORT_COMPILE_COMMANDS YES) 
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set (CMAKE_CXX_STANDARD 14) 
set (BoostInclude /usr/local/include)
set (BoostLib /usr/local/lib)
set (OpensslInclude /usr/local/include)
set (OpensslLib /usr/local/lib64) 
message(STATUS " cur dir = ${CMAKE_CURRENT_SOURCE_DIR}, source dir = ${CMAKE_SOURCE_DIR}")
message(STATUS " openssl dir = ${OpensslLib}")

set(SRCS
    src/main.cpp
    )


link_directories(
    ${BoostLib}
    ${OpensslLib}
    )
# Tell CMake to create the helloworld executable
add_executable(myboostapp ${SRCS})

include_directories(
    ${BoostInclude}
    ${OpensslInclude}
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_SOURCE_DIR}/src
    )


target_link_libraries(myboostapp
    boost_filesystem
    boost_date_time
    pthread
    dl
    ssl
    crypto
    )


