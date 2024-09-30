cmake_minimum_required(VERSION 3.21)
project(sample VERSION 1.0.0 LANGUAGES CXX)

add_library(sample SHARED)

target_sources(sample PRIVATE src/sample.cpp)

target_compile_features(sample PUBLIC cxx_std_17)

target_include_directories(
  sample # The target library
  PRIVATE src/sample # This will make the include directory available to the library itself
  PUBLIC include  # This will make the include directory available to the users of the library
)

set_target_properties(sample PROPERTIES
  VERSION ${PROJECT_VERSION}
  SOVERSION ${PROJECT_VERSION_MAJOR}

  
  # DEBUG_POSTFIX d
)