cmake_minimum_required(VERSION 3.23)
project(Compressor)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/output/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/output/bin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/output/bin)

set(DEP_DIR ${CMAKE_SOURCE_DIR}/deps)

if(${CMAKE_SYSTEM_NAME} STREQUAL "Darwin")
    set(PLATFORM macos)
elseif(${CMAKE_SYSTEM_NAME} STREQUAL "Windows")
    set(PLATFORM win32)
endif()


set(DYN_LIBS)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_LIST_DIR}/cmakes)
find_package(cxxopts)
find_package(ispc_texcomp)


add_subdirectory(libs)
add_subdirectory(tool)
