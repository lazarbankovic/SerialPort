cmake_minimum_required(VERSION 3.14)

project( SerialPort )

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

add_library(SerialPort STATIC
"src/serial_port.cc"
"src/interface.cc" "src/interface.h"
"src/serial_port_windows.cc" "src/serial_port_windows.h"
"src/serial_port_linux.cc" "src/serial_port_linux.h"
"include/serial_port/types.h" "src/enumeration.h" "src/enumeration.cpp")

target_include_directories (SerialPort PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
