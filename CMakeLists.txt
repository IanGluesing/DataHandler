cmake_minimum_required(VERSION 3.12)
project(main)
set(CMAKE_CXX_STANDARD 17)

include(cmake/MyZmq.cmake)
include(cmake/MyCppZmq.cmake)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/thirdParty
)

add_subdirectory(data_forwarder)
add_subdirectory(data_handler)