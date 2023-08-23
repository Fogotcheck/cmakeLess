cmake_minimum_required(VERSION 3.27)
project(myUnitTest VERSION 0.1.0 LANGUAGES C)

set(HeadMain ./main/main.h)

set(Warnings "-Wall -Wextra -Wshadow -Wpointer-arith -Wbad-function-cast -Wcast-align -Wsign-compare -Waggregate-return -Wstrict-prototypes -Wmissing-prototypes -Wmissing-declarations -Wunused")
set(cFlags "-std=c11 ${Warnings}")
set(CMAKE_C_FLAGS ${cFlags})
file(GLOB_RECURSE SrcTest "./srcTests/*.c")
message("SrcTest::${SrcTest}")

set(count 1)
foreach(X IN LISTS SrcTest)
    set(myUnitTest "test${count}")
    add_executable(${myUnitTest} ${X})
    target_link_libraries(${myUnitTest} myLibs)
    MATH(EXPR count "${count}+1")
endforeach()
