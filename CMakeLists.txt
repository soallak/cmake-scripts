cmake_minimum_required(VERSION 3.14)

project(cmake-scripts VERSION 1.0.0)

configure_file(cmake/cmake-scriptsConfig.cmake
               "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}Config.cmake")

# ls -1 *.cmake | grep -v Find
install(
  FILES afl-fuzzing.cmake
        code-coverage.cmake
        compiler-options.cmake
        c++-standards.cmake
        c-standards.cmake
        dependency-graph.cmake
        doxygen.cmake
        formatting.cmake
        glsl-shaders.cmake
        link-time-optimization.cmake
        prepare-catch.cmake
        sanitizers.cmake
        tools.cmake
  DESTINATION share/${PROJECT_NAME})

install(FILES "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}Config.cmake"
        DESTINATION share/${PROJECT_NAME})

# Cpack
set(CPACK_GENERATOR "RPM")
include(CPack)
