cmake_minimum_required(VERSION 3.20)

project(onnxruntime)

set(CMAKE_CXX_STANDARD 17)

add_library(${PROJECT_NAME} INTERFACE IMPORTED GLOBAL)
target_include_directories(
  ${PROJECT_NAME}
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include/core)
file(GLOB_RECURSE SO_FILES "./*.so")
target_link_libraries(${PROJECT_NAME} INTERFACE ${SO_FILES})
