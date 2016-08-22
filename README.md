# icub-moveit

URDF iCub model ready for MoveIt! in ROS Kinetic

## Environment

All the functionality was tested on machines configured with:

+ Ubuntu 16.04 LTS
+ ROS Kinetic

## Download and Setup

Open a terminal and navigate to the folder where you want to download the package.

Now, run:

    git clone https://github.com/bmagyar/icub-moveit.git

__While MoveIt! hasn't been released to Kinetic, add these to the compilation too__

    git clone https://github.com/ros-planning/geometric_shapes.git
    git clone https://github.com/ros-planning/moveit.git

Now run this in your `src` folder to install dependencies:

    rosdep install --from-paths . --ignore-src --rosdistro kinetic

Finally source the environment:

    source devel/setup.bash

## Compilation

    catkin build

or

    catkin_make

## Running

Standard MoveIt demo:

    roslaunch icub_moveit demo.launch

If you want, you can run the model without a graphical interface by running instead:

    roslaunch icub_moveit functional.launch

You can now plan trajectories for the iCub parts, set a start state, a goal state and hit plan.
Note that you will not be able to execute the trajectory since the main goal of this package is to be able to plan. You can connect this planner to the iCub simulator (or even the real robot) using [this other repository](https://github.com/vislab-tecnico-lisboa/yarp-with-moveit) which is responsible to connect the YARP iCub robot to this planning functionality implemented in ROS.
