cmake_minimum_required(VERSION 2.8.3)
project(icub_controller_interface)

find_package(catkin REQUIRED COMPONENTS
  actionlib
  actionlib_msgs
  control_msgs
  yarp_msgs
  roscpp
)

catkin_package()

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(joint_trajectory_action src/joint_trajectory_action.cpp)
target_link_libraries(joint_trajectory_action ${catkin_LIBRARIES}) 
