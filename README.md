# TurtleBot3 Navigation

This repository contains a Python script for controlling TurtleBot3 using ROS2 Navigation2. The code allows you to:

- Set the **initial pose** of the robot
- Send **navigation goals** to move the robot
- Use **threads** to handle multiple commands simultaneously
- Handle different **robot names** if running multiple robots

---

## Features

- `RobotCommand` class for sending initial poses and navigation goals
- Supports specifying:
  - `robot_name` (string) — name of the TurtleBot3
  - `command_type` (string) — either `"init"` for initial pose or `"goal"` for a navigation goal
  - `coordinates` (dict) — dictionary containing `x`, `y`, `z`, `w` values
- Can be used in **threads** to run multiple commands concurrently
- Publishes initial pose to `/robot_name/initialpose` if there is a robotname else if its a single robot `/initialpose`
- Sends goals to `/robot_name/navigate_to_pose`

---

## Usage
###Commands 
ros2 launch turtlebot3_navigation2 navigation2.launch.py use_sim_time:=True
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py

#Use both of the above commands with 
export TURTLEBOT3_MODEL=burger

###Launch Slam 
ros2 launch slam_toolbox online_async_launch.py

###Run the code
python3 waypointturtlebot.py
