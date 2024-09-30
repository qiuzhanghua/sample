cmake_minimum_required(VERSION 3.21)
project(sample VERSION 1.0.0 LANGUAGES CXX)

add_library(${PROJECT_NAME})
add_library(${PROJECT_NAME}::${PROJECT_NAME} ALIAS ${PROJECT_NAME})

target_sources(sample PRIVATE src/sample.cpp)

target_compile_features(sample PUBLIC cxx_std_17)

target_include_directories(
  ${PROJECT_NAME}
  INTERFACE $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)

set_target_properties(sample PROPERTIES
  VERSION ${PROJECT_VERSION}
  SOVERSION ${PROJECT_VERSION_MAJOR}

  
  # DEBUG_POSTFIX d
)