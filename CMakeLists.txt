cmake_minimum_required(VERSION 3.27)
project(myMain VERSION 0.1.0 LANGUAGES C)

set(HeadMain ./main/main.h)
set(SrcMain ./main/main.c)

set(Warnings "-Wall -Wextra -Wshadow -Wpointer-arith -Wbad-function-cast -Wcast-align -Wsign-compare -Waggregate-return -Wstrict-prototypes -Wmissing-prototypes -Wmissing-declarations -Wunused")
set(cFlags "-std=c11 ${Warnings}")
set(CMAKE_C_FLAGS ${cFlags})

message("cflag::${CMAKE_C_FLAGS}")
add_executable(myMain ${HeadMain} ${SrcMain})
target_link_libraries(myMain myLibs)
add_subdirectory(inc)
add_subdirectory(unitTests)
