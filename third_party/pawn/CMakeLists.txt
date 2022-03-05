cmake_minimum_required(VERSION 3.11)

include(FetchContent)
FetchContent_Declare(
  pawn
  GIT_REPOSITORY https://github.com/pawn-lang/compiler.git
  GIT_TAG 134ad7a836c581546665340aedb59efd4636e269
  SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src
  BINARY_DIR ${CMAKE_CURRENT_BINARY_DIR})

FetchContent_GetProperties(pawn)
if(NOT pawn_POPULATED)
  FetchContent_Populate(pawn)
  # Exclude all targets of the PAWN compiler from the "all" target.
  # Because the PAWN abstract machine does not allow 32-bit cell
  # on 64-bit OS and we do not need this.
  # So pawn-ls only builds compiler driver(pawnc).
  add_subdirectory(${pawn_SOURCE_DIR}/source/compiler EXCLUDE_FROM_ALL)
endif()
