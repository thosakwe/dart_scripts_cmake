cmake_minimum_required(VERSION 3.0.0)
project(foo)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY  ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY  ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY  ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -undefined dynamic_lookup")

include_directories(/usr/local/Cellar/dart/1.24.2/libexec/include)
add_definitions(-DDART_SHARED_LIB=1)
add_library(sample_extension SHARED lib/sample_extension.cc)

install(TARGETS sample_extension DESTINATION lib)