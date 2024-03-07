project(onnxruntime)

add_library(${PROJECT_NAME} INTERFACE IMPORTED GLOBAL)
target_include_directories(
  ${PROJECT_NAME} 
  INTERFACE include 
  INTERFACE include/onnxruntime
  INTERFACE include/onnxruntime/core/session)
file(GLOB_RECURSE SO_FILES "./lib/*.so")
target_link_libraries(${PROJECT_NAME} INTERFACE ${SO_FILES})

add_files(${OUT_3RDLIB} "lib/lib*")
