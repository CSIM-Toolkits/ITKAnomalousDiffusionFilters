cmake_minimum_required(VERSION 3.10.2)
project(AnomalousDiffusionFilters)

set(AnomalousDiffusionFilters_LIBRARIES AnomalousDiffusionFilters)

if(NOT ITK_SOURCE_DIR)
  find_package(ITK REQUIRED)
  list(APPEND CMAKE_MODULE_PATH ${ITK_CMAKE_DIR})
  include(ITKModuleExternal)
else()
  itk_module_impl()
endif()
