cmake_minimum_required(VERSION 3.25)
project(BearLibTerminalGame)

set(CMAKE_CXX_STANDARD 14)

list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/CMake")

find_package(BLT REQUIRED) # я здесь изменил оригинальный код от coding garden (в оригинале было "find_package(BearLibTerminal REQUIRED)"), потому что clion некритично, но все-же ругался. А так-же я изменил название файла с FindBearLibTerminal.cmake на FindBLT.cmake
include_directories(SYSTEM ${BLT_INCLUDE_DIRS})

add_executable(${PROJECT_NAME} ./src/main.cpp)

target_link_libraries(${PROJECT_NAME} ${BLT_LIBRARIES})

file(COPY ${BLT_LIBRARY} DESTINATION ${CMAKE_CURRENT_BINARY_DIR})