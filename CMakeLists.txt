cmake_minimum_required(VERSION 3.21)
project(learn)

set(CMAKE_CXX_STANDARD 14)

#add_executable(learn main.cpp)
#add_executable(chapter1 chapter1/chap1.cpp chapter1/chap1.h)
file (GLOB_RECURSE files *.cpp)
foreach (file ${files})
    string(REGEX REPLACE ".+/(.+)\\..*" "\\1" exe ${file})
    add_executable (${exe} ${file})
    message (\ \ \ \ --\ src/${exe}.cpp\ will\ be\ compiled\ to\ bin/${exe})
endforeach ()