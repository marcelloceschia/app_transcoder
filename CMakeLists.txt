cmake_minimum_required (VERSION 2.6)
project(app_transcoder)

SET(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/CMakeModules")



find_package(avcodec REQUIRED)
find_package(asterisk REQUIRED)

add_library(app_transcoder SHARED app_transcoder.c)
set_target_properties(app_transcoder PROPERTIES PREFIX "")

target_link_libraries (app_transcoder avcodec) 


install (TARGETS app_transcoder DESTINATION ${ASTERISK_LIBRARY_DIR})
