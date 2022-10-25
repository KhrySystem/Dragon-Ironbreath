cmake_minimum_required(VERSION 3.24)

set(CXX_FILES src/init.cpp)

if(DRAGON_BUILD_SHARED)
	add_library(ironbreath SHARED ${CXX_FILES})
else() 
	add_library(ironbreath STATIC ${CXX_FILES})
endif()
target_include_directories(ironbreath PUBLIC ${Dragon_INCLUDE_DIRS})
target_link_libraries(ironbreath PUBLIC ${Boost_LIBRARIES} ${Vulkan_LIBRARIES})
add_library(Dragon::Ironbreath ALIAS ironbreath)