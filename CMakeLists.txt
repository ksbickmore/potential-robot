cmake_minimum_required(VERSION 3.24)
project(potential-robot VERSION 1.0.0 LANGUAGES C)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
SET(CMAKE_C_STANDARD 11)

cmake_policy(SET CMP0083 NEW)
cmake_policy(SET CMP0063 NEW)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/export/${CMAKE_BUILD_TYPE}/bin")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/export/${CMAKE_BUILD_TYPE}/lib")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/export/${CMAKE_BUILD_TYPE}/lib")

set(CMAKE_C_VISIBILITY_PRESET hidden)
set(C_VISIBILITY_PRESET hidden)

set(RELEASE_COMPILE_OPTIONS -Werror -Wall -O3 -flto -fdata-sections -ffunction-sections)
set(DEBUG_COMPILE_OPTIONS -Werror -Wall -g)
set(RELEASE_LINK_OPTIONS -Wl,--gc-sections,-s)

add_subdirectory(src)