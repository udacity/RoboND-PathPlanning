[![Udacity - Robotics NanoDegree Program](https://s3-us-west-1.amazonaws.com/udacity-robotics/Extra+Images/RoboND_flag.png)](https://www.udacity.com/robotics)

# RoboND-PathPlanning
A wall_follower ROS C++ node for the Home Service Robot Project. This node will autonomously drive your robot close to the walls while avoiding obstacles on its path.

### Basic Idea
A wall follower algorithm is a common algorithm that solves mazes. This algorithm is also known as the left-hand rule algorithm or the right-hand rule algorithm depending on which is your priority. The wall follower can only solve mazes with connected walls, where the robot is guaranteed to reach the exit of the maze after traversing close to walls. You will implement this basic algorithm in your environment to travel close to the walls and autonomously map it.

Here’s the wall follower algorithm(the left-hand one) at a high level:
``` 
If left is free:
    Turn Left
Else if left is occupied and straight is free:
    Go Straight
Else if left and straight are occupied:
    Turn Right 
Else if left/right/straight are occupied or you crashed:
    Turn 180 degrees
```

This algorithm has a lot of disadvantages because of the restricted space it can operate in. In other words, this algorithm will fail in open or infinitely large environments. Usually, the best algorithms for autonomous mapping are the ones that go in pursuit of undiscovered areas or unknown grid cells.

### Task List
Here's a detailed task list of the steps you should take in order to implement this package with your home service robot to autonomously map an environment:
1. Create a **wall_follower** package.
2. Create a **wall_follower** C++ node by cloning this repo.
3. Edit the wall_follower C++ **node name** and change it to **wall_follower**.
4. Edit the wall_follower C++ subscriber and publisher **topics name**.
5. Write a **wall_follower.sh** shell script that launch the **turtlebot_world.launch**, **gmapping_demo.launch**, **view_navigation.launch**, and the **wall_follower** node.
6. Edit the **CMakeLists.txt** file and add directories, executable, and target link libraries.
7. Build your **catkin_ws**.
8. Run your **wall_follower.sh** shell script to autonomously map the environment.
9. Once you are satisfied with the map, kill the wall_follower terminal and save your map in both **pgm** and **yaml** formats in the **World** directory of your **catkin_ws/src**.
