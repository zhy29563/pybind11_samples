cmake_minimum_required (VERSION 3.18 FATAL_ERROR)
project(pybind11_samples)
 
#SET(CMAKE_CXX_STANDARD 11)
#SET(CMAKE_CXX_STANDARD_REQUIRED True)

#SET(CMAKE_BUILD_TYPE Release)
#MESSAGE(STATUS "Build Type: ${CMAKE_BUILD_TYPE}")

if (NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
  MESSAGE("Setting build type to 'RelWithDebInfo' as none was specified")
  SET(CMAKE_BUILD_TYPE RelWithDebInfo CACHE STRING "Choose the type of build." FORCE)
  SET_PROPERTY(CACHE CMAKE_BUILD_TYPE "Debug" "Release" "MinSizeRel" "RelWithDebInfo")
endif()

if (NOT DEFINED CMAKE_DEBUG_POSTFIX)
  SET(CMAKE_DEBUG_POSTFIX "_d")
endif()

add_library(pybind11_sample SHARED sample03.cpp)

set_target_properties(pybind11_sample
  PROPERTIES
  CXX_STANDARD 11
  CXX_STANDARD_REQUIRED ON
  PREFIX ""
  SUFFIX ".pyd"
)
target_include_directories(pybind11_sample 
                           PUBLIC 
                           "C:/Program Files/Python38/"
                           "C:/Program Files/Python38/include"
                           ${CMAKE_CURRENT_SOURCE_DIR}/pybind11/include/)

target_link_directories(pybind11_sample PUBLIC "C:/Program Files/Python38/libs")

if("${CMAKE_BUILD_TYPE}" STREQUAL "Debug")
  target_link_libraries(pybind11_sample python3_d.lib python38_d.lib)
endif()

if("${CMAKE_BUILD_TYPE}" STREQUAL "Release")
  target_link_libraries(pybind11_sample python3.lib python38.lib)
endif()