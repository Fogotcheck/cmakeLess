cmake_minimum_required(VERSION 3.27)
project(myLibs VERSION 0.1.0 LANGUAGES C)

file(GLOB_RECURSE Head "./head/*.h")
file(GLOB_RECURSE Src "./src/*.c")
message("Head::${Head}\nSrc::${Src}")

add_library(myLibs ${Head} ${Src})

