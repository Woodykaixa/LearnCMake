cmake_minimum_required(VERSION 3.16)
project(
    LearnCMakeLab4 
    VERSION 1.0 
    DESCRIPTION "Learn CMake Lab4 - Programming in CMake" 
)

set(MY_VARIABLE "hello")
set(MY_LIST_VARIABLE "hello" "world" "!!")
message(STATUS "MY_VARIABLE is ${MY_VARIABLE}")
message(STATUS "MY_LIST_VARIABLE is " "${MY_LIST_VARIABLE}")

function(my_func)
    message(STATUS "my_func")
    foreach(list_item ${ARGV})
        message(STATUS "\t${list_item}")
    endforeach()
endfunction()

my_func(${MY_LIST_VARIABLE})

message(STATUS "Result of command \"gcc --help|grep W\"")
execute_process(
    COMMAND gcc --help
    OUTPUT_FILE OUT_TXT
)

execute_process(
    COMMAND grep W
    INPUT_FILE OUT_TXT
    RESULT_VARIABLE result
)

message(STATUS "result is ${result}")

message(STATUS "Result of command \"ls\"")

execute_process(
    COMMAND ls
    RESULT_VARIABLE RESULT
    OUTPUT_VARIABLE OUTPUT
    ERROR_VARIABLE ERROR
)

message(STATUS "RESULT is ${RESULT}")
message(STATUS "OUTPUT is ${OUTPUT}")
message(STATUS "ERROR is ${ERROR}")

message(STATUS "Result of command \"ls ./s\"")

execute_process(
    COMMAND ls ./s
    RESULT_VARIABLE RESULT
    OUTPUT_VARIABLE OUTPUT
    ERROR_VARIABLE ERROR
)

message(STATUS "RESULT is ${RESULT}")
message(STATUS "OUTPUT is ${OUTPUT}")
message(STATUS "ERROR is ${ERROR}")
