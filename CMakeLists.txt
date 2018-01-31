cmake_minimum_required(VERSION 3.0.0)
project(foo)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
add_executable(hello lib/hello.cc)

install(TARGETS hello DESTINATION lib)