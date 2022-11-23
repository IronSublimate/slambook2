cmake_minimum_required (VERSION 3.5)
project (slambook2 CXX)

#add_subdirectory(3rdparty/ceres-solver)
#add_subdirectory(3rdparty/DBoW3)
#add_subdirectory(3rdparty/g2o)
#add_subdirectory(3rdparty/googletest)
#add_subdirectory(3rdparty/Pangolin)
#add_subdirectory(3rdparty/Sophus)
# cmake -B build/g2o -DCMAKE_INSTALL_PREFIX=install 3rdparty/g2o
# cmake --build build/g2o -j20
# cmake --build build/g2o --target install

# cmake -B build/Pangolin -DCMAKE_INSTALL_PREFIX=install 3rdparty/Pangolin
# cmake --build build/Pangolin -j20
# cmake --build build/Pangolin --target install

# cmake -B build/Sophus -DCMAKE_INSTALL_PREFIX=install 3rdparty/Sophus
# cmake --build build/Sophus -j20
# cmake --build build/Sophus --target install

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "-march=native")

add_subdirectory(ch2)
add_subdirectory(ch3)
add_subdirectory(ch4)
add_subdirectory(ch5)
add_subdirectory(ch6)
add_subdirectory(ch7)
add_subdirectory(ch8)
add_subdirectory(ch9)
add_subdirectory(ch10)
add_subdirectory(ch11)
add_subdirectory(ch12)
add_subdirectory(ch13)
