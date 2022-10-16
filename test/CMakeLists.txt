cmake_minimum_required(VERSION 3.14)

project(cmake-scripts-tests)

find_package(cmake-scripts REQUIRED)

set(INCLUDE_FILES
    afl-fuzzing
    code-coverage
    compiler-options
    c++-standards
    c-standards
    dependency-graph
    doxygen
    formatting
    glsl-shaders
    link-time-optimization
    prepare-catch
    sanitizers
    tools)
foreach(F IN LISTS INCLUDE_FILES)
  message(STATUS "Including ${F}")
  include(${F})
endforeach()
