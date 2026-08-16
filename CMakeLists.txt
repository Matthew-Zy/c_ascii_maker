cmake_minimum_required(VERSION 3.15)

project(
    C-Ascii-Maker
    DESCRIPTION "Ascii generator written in C, by a pretty cool guy I think"
    LANGUAGES C)

set(exec_name "cascii")
file(GLOB SOURCE_FILES CONFIGURE_DEPENDS "src/*.c")

add_executable(${exec_name} ${SOURCE_FILES})

target_include_directories(${exec_name} PRIVATE include)

if(NOT WIN32)
    target_link_libraries(${exec_name} PRIVATE m)
endif()

if(UNIX)
    target_link_libraries(${exec_name} PRIVATE m)
endif()