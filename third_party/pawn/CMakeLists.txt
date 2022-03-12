# Copyright 2022 MaBling <akck0918@gmail.com>. All rights reserved.
# Use of this source code is governed by a BSD-style license that can be
# found in the LICENSE file.

cmake_minimum_required(VERSION 3.11)

include(FetchContent)
FetchContent_Declare(
  pawn
  GIT_REPOSITORY https://github.com/qoor/pawn.git
  GIT_TAG 9ce20d434c4784ff60b1a9bf9f5131b12c3f443a
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
