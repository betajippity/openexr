# SPDX-License-Identifier: BSD-3-Clause
# Copyright (c) Contributors to the OpenEXR Project.

add_executable(website_src all.cpp)
if (CMAKE_COMPILER_IS_GNUCC AND CMAKE_CXX_COMPILER_VERSION VERSION_LESS 8.0)
    target_link_libraries(website_src OpenEXR::OpenEXR stdc++fs)
else()
target_link_libraries(website_src OpenEXR::OpenEXR)
endif()
set_target_properties(website_src PROPERTIES
  RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
