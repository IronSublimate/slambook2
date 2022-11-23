cmake_minimum_required(VERSION 2.8)
project(pose_graph)

#set(CMAKE_BUILD_TYPE "Release")
#set(CMAKE_CXX_FLAGS "-std=c++11 -O2")

#list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake_modules)

# Eigen
find_package(Eigen3 REQUIRED)
include_directories(${EIGEN3_INCLUDE_DIR})

# sophus 
find_package(Sophus REQUIRED)
include_directories(${Sophus_INCLUDE_DIRS})

# g2o 
find_package(g2o REQUIRED)
include_directories(${G2O_INCLUDE_DIRS})

find_package(fmt REQUIRED)

find_package(GTSAM REQUIRED)
include_directories(${GTSAM_INCLUDE_DIRS})


add_executable(pose_graph_g2o_SE3 pose_graph_g2o_SE3.cpp)
target_link_libraries(pose_graph_g2o_SE3
        g2o_core g2o_stuff g2o_types_slam3d
        ${CHOLMOD_LIBRARIES}
        fmt::fmt
        )

add_executable(pose_graph_g2o_lie pose_graph_g2o_lie_algebra.cpp)
target_link_libraries(pose_graph_g2o_lie
        g2o_core g2o_stuff
        ${CHOLMOD_LIBRARIES}
        ${Sophus_LIBRARIES}
        fmt::fmt
        )

#message(1:${GTSAM_LIBS} 2:${GTSAM_LIBRARIES})

add_executable(pose_graph_gtsam pose_graph_gtsam.cpp)
target_link_libraries(pose_graph_gtsam
        gtsam
        OpenMP::OpenMP_CXX
        ${Sophus_LIBRARIES}
        )