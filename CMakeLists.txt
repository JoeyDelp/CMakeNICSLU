cmake_minimum_required(VERSION 3.11 FATAL_ERROR)

project(CMakeNICSLU VERSION 1.0.0 LANGUAGES C)

option(NICS_INT64 "Compile with 64-bit" ON)

if(NICS_INT64)
	add_definitions("-DNICS_INT64")
endif()

include(${PROJECT_SOURCE_DIR}/cmake/setup_nicslu.cmake)

file(GLOB_RECURSE nicslu_sources CONFIGURE_DEPENDS "src/*.c")

nicslu_target(nicslu "${nicslu_sources}")