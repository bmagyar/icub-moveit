cmake_minimum_required(VERSION 2.8)
project(icub_ros)

find_package(catkin REQUIRED 
  std_msgs 
  sensor_msgs
  roscpp
  yarp_msgs
)

catkin_package(
  INCLUDE_DIRS include
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

add_executable(icub_ros src/IcubRosInterface.cpp)
target_link_libraries(icub_ros ${catkin_LIBRARIES})
