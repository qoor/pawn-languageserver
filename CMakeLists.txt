cmake_minimum_required(VERSION 3.11)

project(pawn-ls
  VERSION 0.0.1
  DESCRIPTION "The language server implementation for PAWN Language."
  LANGUAGES C CXX)

option(CMAKE_EXPORT_COMPILE_COMMANDS "Exports compile_commands.json" ON)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib")

set(PAWN_LS_COMMON_INCLUDE_DIR
  ${CMAKE_CURRENT_SOURCE_DIR}
  ${CMAKE_CURRENT_BINARY_DIR})
