
cmake_minimum_required(VERSION 3.4.1)

project(IntelRealsenseSample)

set( CMAKE_CXX_FLAGS "-std=c++11" )

set( CMAKE_BUILD_TYPE "Debug" )

find_package(OpenCV REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})

link_libraries(
    realsense2
    opencv_core
    opencv_highgui
)

add_executable(color_sample ./src/ColorSample.cpp)
add_executable(ir_sample ./src/IrSample.cpp)
add_executable(depth_sample ./src/DepthSample.cpp)

target_link_libraries(color_sample LINK_PRIVATE ${OpenCV_LIBS})
target_link_libraries(ir_sample LINK_PRIVATE ${OpenCV_LIBS})
target_link_libraries(depth_sample LINK_PRIVATE ${OpenCV_LIBS})