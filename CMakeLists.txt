cmake_minimum_required(VERSION 3.10)
project(ProjectR)

set(CMAKE_CXX_STANDARD 17)

# Find Vulkan
find_package(Vulkan REQUIRED)

# Include GLFW and GLM from local project directory
include_directories(${CMAKE_SOURCE_DIR}/include)

# Add source files
add_executable(ProjectR main.cpp)

# Link libraries
set(GLFW3_LIBRARY ${CMAKE_SOURCE_DIR}/libs/libglfw.so)
target_link_libraries(ProjectR ${Vulkan_LIBRARIES} ${GLFW3_LIBRARY})
