## set target project
file(GLOB target_src "*.h" "*.cpp")
add_executable(${subdir} ${target_src})
## set link libraries
target_link_libraries(${subdir} ${libraries})
## add local source directory to include paths
target_include_directories(${subdir} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

## copy shaders to build folder
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/shader.vert DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/shader.frag DESTINATION ${CMAKE_CURRENT_BINARY_DIR})