cmake_minimum_required(VERSION 3.5)

add_executable(scratch main.cpp)

set_property(TARGET scratch PROPERTY CXX_STANDARD 14)
set_property(TARGET scratch PROPERTY CXX_STANDARD_REQUIRED ON)