# Excerpt and slightly changed from 
# https://stackoverflow.com/questions/23163075/how-to-compile-an-mpi-included-c-program-using-cmake

cmake_minimum_required(VERSION 3.0)

project(main)

find_package(MPI REQUIRED)
#  include_directories(SYSTEM ${MPI_INCLUDE_PATH})
# add this line only when you are using openmpi which has a different c++ bindings
add_definitions(-DOMPI_SKIP_MPICXX)

# Use imported targets would make things much eazier. Thanks Levi for pointing it out.
add_executable(main main.cpp)
target_link_libraries(main
  PRIVATE
  MPI::MPI_C)

# Old way.
#target_link_libraries(main
# PRIVATE
# ${MPI_C_LIBRARIES})

install(TARGETS main DESTINATION "${CMAKE_SOURCE_DIR}/exe")
