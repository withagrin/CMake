cmake_minimum_required(VERSION 3.7)
project(WithC CUDA C)

set(CMAKE_CUDA_ARCHITECTURES 30)

add_executable(CudaWithC main.c cuda.cu)

if(APPLE)
  # Help the static cuda runtime find the driver (libcuda.dyllib) at runtime.
  set_property(TARGET CudaWithC PROPERTY BUILD_RPATH ${CMAKE_CUDA_IMPLICIT_LINK_DIRECTORIES})
endif()
