cmake_minimum_required( VERSION 2.8 )
project( visualizeGeometry )

#set(CMAKE_CXX_FLAGS "-std=c++11")

# 添加Eigen头文件
#include_directories( "/usr/include/eigen3" )
find_package(Eigen3 REQUIRED)
include_directories(${EIGEN3_INCLUDE_DIR})

# 添加Pangolin依赖
find_package(Pangolin REQUIRED)
include_directories(${Pangolin_INCLUDE_DIRS} )
#message(hyx :${Pangolin_INCLUDE_DIRS} )

add_executable( visualizeGeometry visualizeGeometry.cpp )
target_link_libraries( visualizeGeometry ${Pangolin_LIBRARIES} )
