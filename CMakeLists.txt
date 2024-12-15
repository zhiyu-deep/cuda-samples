cmake_minimum_required(VERSION 3.18)
project(cuda_samples CXX CUDA)

set(CMAKE_CXX_STANDARD 14)

file(GLOB commons Common/*.cpp)
add_library(common SHARED ${commons})

# for ipc.
add_executable(cudaIPC Samples/0_Introduction/simpleIPC/simpleIPC.cu)
target_include_directories(cudaIPC PRIVATE Common)
target_link_libraries(cudaIPC PRIVATE commons)
