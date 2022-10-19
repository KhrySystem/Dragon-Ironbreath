cmake_minimum_required(VERSION 3.24)

add_library(ironbreath SHARED src/metal_init.cpp)
target_include_directories(ironbreath PUBLIC ${Dragon_INCLUDE_DIRS})
target_link_libraries(ironbreath PUBLIC ${Dragon_LINK_LIBRARIES})
add_library(Dragon::Ironbreath ALIAS ironbreath)
list(APPEND Dragon_LINK_LIBRARIES Dragon::Ironbreath)