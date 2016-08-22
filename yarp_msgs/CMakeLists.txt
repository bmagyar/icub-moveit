cmake_minimum_required(VERSION 2.8)
project(yarp_msgs)

# generate the messages and the actionlib server for ROS
find_package(catkin REQUIRED 
  std_msgs
  message_generation
  message_runtime
)

add_message_files(DIRECTORY msg
                  FILES JointValues.msg)

generate_messages(DEPENDENCIES std_msgs)

# define the project
catkin_package(CATKIN_DEPENDS std_msgs)
