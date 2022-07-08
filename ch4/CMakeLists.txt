cmake_minimum_required(VERSION 3.0)
project(useSophus)

# 为使用 sophus，需要使用find_package命令找到它
find_package(Sophus REQUIRED)
find_package(fmt REQUIRED)

# Eigen
find_package(Eigen3 REQUIRED)
include_directories(EIGEN3_INCLUDE_DIR)

add_executable(useSophus useSophus.cpp)
target_link_libraries(useSophus fmt::fmt Sophus::Sophus)

add_subdirectory(example)
