cmake_minimum_required(VERSION 2.8)
enable_testing()
project(test-cxx-force)
include(../../PrecompiledHeader.cmake)
if(MSVC)
  set(pch_source test-pch.cpp)
endif()
add_executable(test-cxx-force test-cxx-force.cpp test-pch.h ${pch_source})
add_precompiled_header(test-cxx-force test-pch.h FORCEINCLUDE)
add_test(test-cxx-force test-cxx-force)
