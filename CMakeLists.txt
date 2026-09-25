cmake_minimum_required (VERSION 3.23)

project(lslver LANGUAGES C CXX)

find_package(LSL CONFIG REQUIRED)

add_executable(lslver lslver.c)

target_link_libraries(lslver PRIVATE LSL::lsl)

get_target_property(LSL_TYPE LSL::lsl TYPE)
if(WIN32 AND LSL_TYPE STREQUAL "SHARED_LIBRARY")
    add_custom_command(TARGET lslver POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy_if_different
            "$<TARGET_FILE:LSL::lsl>"
            "$<TARGET_FILE_DIR:lslver>"
    )
endif()
