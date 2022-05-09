cmake_minimum_required(VERSION 3.0)

project(Test_Project C) 

include_directories(include)

add_library(myLib src/A.c src/B.c)

add_executable(myExe src/myExe.c)
target_link_libraries(myExe myLib)


