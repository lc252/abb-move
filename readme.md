# Moveit! with an ABB-IRB1200-7/0.7

This repo was used to get familiar with Moveit! by simulating the ABB robot in the lab. It was then extended to communicate with a Unity application to render the ABB robot in Unity and the HoloLens2. 

Implementation of the tutorials on:
- https://moveit.ros.org
- https://github.com/ros-planning/moveit_tutorials
- https://github.com/Unity-Technologies/Unity-Robotics-Hub

Packages adapted from:
- https://github.com/ros-industrial/abb_experimental
- https://github.com/ros-industrial/abb
- https://github.com/Unity-Technologies/ROS-TCP-Endpoint

Other ROS dependencies:
- moveit_opw_kinematics_plugin
- rviz_visual_tools

# Usage

To play around with the robot and simulate movement run `roslaunch abb_irb1200_7_70_moveit_config demo.launch` in a terminal. Move the goal state position in RViz and press Plan and Execute. Two ghosts will track towards the orange goal state, the first is the planned path and the second is the excecuted path.
To begin ros-unity communication run `roslaunch ros_tcp_endpoint endpoint.launch tcp_ip:=[IP_ADDRESS]` in a new terminal.
On the HoloLens, run the ABB-Simulation (link) application. Look at the QR to locate the robot, first a square should appear, look away and then look back. The simulated robot will be in the pose that is currently being published. To move the robot, drag the end effector in the RViz simulation and hit Plan and Execute. Note that the orange goal pose, green start pose and planning pose are not published or visualised in the HoloLens, only the executed, "real" pose is.

# Future Plans

- Use the urdf importer package from Unity-Robotics-Hub
- Move the robot end effector in Unity
- Visualise the goal pose as well as current pose
- Visualise null space exploration
- Interact with individial links
