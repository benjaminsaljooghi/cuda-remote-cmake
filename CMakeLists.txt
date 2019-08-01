# CMakeList.txt : CMake project for cmakecuda, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.11)
enable_language(CUDA) 

include_directories(CUDA_INCLUDE_DIRS)
find_library(CUDART_LIBRARY cudart ${CMAKE_CUDA_IMPLICIT_LINK_DIRECTORIES})
add_executable(binary_linking_to_cudart "helloworld.cu")
target_include_directories(binary_linking_to_cudart PUBLIC ".")
target_include_directories(binary_linking_to_cudart PRIVATE ${CMAKE_CUDA_TOOLKIT_INCLUDE_DIRECTORIES})
target_link_libraries(binary_linking_to_cudart ${CUDART_LIBRARY})


# Add source to this project's executable.

#add_executable (helloworld "helloworld.cu")

# TODO: Add tests and install targets if needed.
