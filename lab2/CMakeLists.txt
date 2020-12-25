cmake_minimum_required(VERSION 3.16)
project(LearnCMakeLab2 VERSION 1.0 DESCRIPTION "Learn CMake Lab2 - Multi File Executable" LANGUAGES CXX)

#[[
The most simple way is using:
`add_executable(lab2 main.cpp math.cpp math.h)`
But I'd like to try the add_library command
]]

add_library(mathlib STATIC math.h math.cpp)
add_executable(lab2 main.cpp)
target_link_libraries(lab2 PUBLIC mathlib)
