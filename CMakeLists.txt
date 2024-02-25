cmake_minimum_required(VERSION 3.17)
project(scikit_build_core_tmp_install_issue_minimal_example Fortran)

enable_language(Fortran)

find_program(FYPP fypp)

add_custom_command(
        OUTPUT "${CMAKE_CURRENT_BINARY_DIR}/main.f90"
        COMMAND ${FYPP} "${CMAKE_CURRENT_SOURCE_DIR}/main.fpp" "${CMAKE_CURRENT_BINARY_DIR}/main.f90"
        MAIN_DEPENDENCY "${CMAKE_CURRENT_SOURCE_DIR}/main.fpp"
        VERBATIM)

add_executable(scikit_build_core_tmp_install_issue_minimal_example main.f90)
