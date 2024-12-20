cmake_minimum_required(VERSION 3.21)
cmake_policy(SET CMP0177 NEW)

project(SkyrimCMake)

include(GNUInstallDirs)

configure_file(cmake/Config.cmake.in ${PROJECT_NAME}Config.cmake @ONLY)

install(
    FILES
    cmake/Skyrim.cmake
    "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}Config.cmake"
    DESTINATION "${CMAKE_INSTALL_LIBDIR}/cmake"
)

install(DIRECTORY SkyrimCMake DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}/..")
