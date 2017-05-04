cmake_minimum_required(VERSION 2.8.3)
project(gransac)

#catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES ${PROJECT_NAME}
#)

include_directories( include )

configure_file("${CMAKE_SOURCE_DIR}/cmake/gransac-config.cmake.in"
               "${CMAKE_BINARY_DIR}/gransac-config.cmake" @ONLY)

message("DERERERERERERERE" ${CMAKE_BINARY_DIR} " " ${CMAKE_MODULE_PATH} )

install(FILES 
    "${CMAKE_SOURCE_DIR}/include/AbstractModel.hpp" 
    "${CMAKE_SOURCE_DIR}/include/GRANSAC.hpp" 
DESTINATION include/${PROJECT_NAME})

install(FILES "${CMAKE_BINARY_DIR}/gransac-config.cmake" DESTINATION "lib/cmake/${PROJECT_NAME}")

export(PACKAGE ${PROJECT_NAME})