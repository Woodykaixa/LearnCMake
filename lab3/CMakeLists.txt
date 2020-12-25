cmake_minimum_required(VERSION 3.16)
project(
    LearnCMakeLab3 
    VERSION 1.0 
    DESCRIPTION "Learn CMake Lab3 - Multi File Executable with Custom IncludePath" 
    LANGUAGES CXX
)

#[[
 I've tried CMake before, and I know that I can add an CMakeLists.txt in `inc` 
 to make it a subdirectory(or module? I don't know). But I haven't found it in
 this tutorial, so I just use `inc/my_math.h` here.
]]

add_library(mathlib STATIC inc/my_math.h inc/my_math.cpp)
target_include_directories(mathlib PUBLIC inc)
add_executable(lab3 main.cpp)
target_link_libraries(lab3 PUBLIC mathlib)

