cmake_minimum_required(VERSION 3.27)
project(static_hello_test)

set(CMAKE_CXX_STANDARD 23)

file(GLOB_RECURSE LIB_SOURCES "*.cpp")

add_library(${PROJECT_NAME} STATIC ${LIB_SOURCES})
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

## Create a Config.cmake file for the library
#include(CMakePackageConfigHelpers)
#write_basic_package_version_file(
#        ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}ConfigVersion.cmake
#        VERSION 1.0
#        COMPATIBILITY AnyNewerVersion
#)
#
#configure_package_config_file(
#        ${CMAKE_CURRENT_SOURCE_DIR}/Config.cmake.in
#        ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}Config.cmake
#        INSTALL_DESTINATION ${CMAKE_CURRENT_BINARY_DIR}
#)
#
## Install the library and the Config.cmake file
#install(TARGETS ${PROJECT_NAME}
#        EXPORT ${PROJECT_NAME}Targets
#        LIBRARY DESTINATION lib
#        ARCHIVE DESTINATION lib
#        RUNTIME DESTINATION bin
#        INCLUDES DESTINATION include
#)
#
#install(EXPORT ${PROJECT_NAME}Targets
#        FILE ${PROJECT_NAME}Config.cmake
#        DESTINATION lib/cmake/${PROJECT_NAME}
#)