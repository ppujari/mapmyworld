# Project 4: Map My World

This project is part of Udacity Robotics Software Engineer Nanodegree.I used my robot and the world from previous project. Added depth camera to the robot to use in mapping process. I used RTAB-Map package to create the map of the world.

<table style="width:100%">
  <tr>
    <th><p>
           <img src="images/3D_map.png"
            alt="3D map" width="400" height="200"></a>
           <br>3D Map
        </p>
    </th>
    <th><p>
           <img src="images/2D_map.png"
            alt="2D map" width="200" height="200"></a>
           <br>2D Map
      </p>
    </th>
  </tr>
  <tr>
    <th><p>
           <img src="images/occupancy_grid.png"
            alt="occupancy grid" width="400" height="200"></a>
           <br>Occupancy Grid
      </p>
    </th>
    <th><p>
           <img src="images/features.png"
            alt="features" width="200" height="200"></a>
           <br>Detected Features
      </p>
    </th>
  </tr>
</table>


## Prerequisites
1. ROS (Melodic or Kinetic), Gazebo on Linux
2. CMake & g++/gcc
3. Install `rtabmap-ros` package `$ sudo apt-get install ros-${ROS_DISTRO}-rtabmap-ros`

## Build and Launch

1. Clone project and initialize a catkin workspace
```
$ mkdir catkin_ws && cd catkin_ws
$ git clone https://github.com/ppujari/mapmyworld.git
$ mv RoboND-Map-My-World src
$ cd src && catkin_init_workspace
```

2. Within the `catkin_ws/src` folder, clone the `teleop` project
```
$ git clone https://github.com/ros-teleop/teleop_twist_keyboard
```

3. Move back to `catkin_ws\` and build
```
$ cd ..
$ catkin_make
```

4. Launch the world and robot
```
$ source devel/setup.bash
$ roslaunch my_robot world.launch
```

5. Open another terminal (Ctrl+Shift+T), and launch the `mapping.launch` file. 
Here, the rtabmap-ros package will be launched.
```
$ source devel/setup.bash
$ roslaunch my_robot mapping.launch
```

6. Open another terminal, and run the `teleop` node.
```
$ source devel/setup.bash
$ rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

7. Click on this terminal, type keyboard to navigate the robot around. Navigate 
the robot to scan its surrounding environment. The rtabmap-ros package will save
the resulted map with the localized trajectory of the robot in a database file 
`~/.ros/rtabmap.db`.

8. You can download the database file from google drive and unzip the file before view. Git allows only 50mb this is 75mb after gzip also.
```
$ rtabmap-databaseViewer https://drive.google.com/file/d/1S6I586E-kMIG1uJ3Gn2phPxaYD7cNpdx/view?usp=sharing
```

Shows generated 2D map and 3D loop closure example. Click to download database file of created map.    
 [screenshot.png](images/screenshot.png).
