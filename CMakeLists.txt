cmake_minimum_required (VERSION 3.23)

project(lslver LANGUAGES C CXX)

find_package(LSL CONFIG REQUIRED)

add_executable(lslver lslver.c)

target_link_libraries(lslver PRIVATE LSL::lsl)
