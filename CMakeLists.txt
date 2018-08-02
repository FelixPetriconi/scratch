cmake_minimum_required(VERSION 3.5)

add_executable(scratch main.cpp)

set_property(TARGET scratch PROPERTY CXX_STANDARD 17)
set_property(TARGET scratch PROPERTY CXX_STANDARD_REQUIRED ON)

set( Boost_MULTITHREADED ON ) 
set( Boost_USE_STATIC_LIBS ON )

find_package( Boost 1.66.0 COMPONENTS thread)

set( CMAKE_THREAD_PREFER_PTHREAD TRUE )

target_include_directories(scratch PUBLIC "../libraries")

set(BENCHMARK_ENABLE_TESTING OFF CACHE BOOL "Suppressing benchmark's tests" FORCE)
add_subdirectory("benchmark-1.4.1")
target_link_libraries(scratch benchmark)