
## Refs

- [Turtlebot 3](https://github.com/ROBOTIS-GIT/turtlebot3)

## Setup

1. Install ROS (melodic)

2. Install some deps

```bash
sudo apt-get install \
ros-melodic-joy \
ros-melodic-teleop-twist-joy \
ros-melodic-teleop-twist-keyboard \
ros-melodic-laser-proc \
ros-melodic-rgbd-launch \
ros-melodic-depthimage-to-laserscan \
ros-melodic-rosserial-arduino \
ros-melodic-rosserial-python \
ros-melodic-rosserial-server \
ros-melodic-rosserial-client \
ros-melodic-rosserial-msgs \
ros-melodic-amcl \
ros-melodic-map-server \
ros-melodic-move-base \
ros-melodic-urdf \
ros-melodic-xacro \
ros-melodic-compressed-image-transport \
ros-melodic-rqt-image-view \
ros-melodic-gmapping \
ros-melodic-navigation \
ros-melodic-interactive-markers
```

3. Install turtlebot3 packages

```bash
export _cws=~/projects/dyson-bot/catkin_ws
cd ${_cws}/src/
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
cd ${_cws} && catkin_make
```

## Simulation with gazebo

- Specify turtlebot model

    ```bash
    export TURTLEBOT3_MODEL='burge'
    # or
    export TURTLEBOT3_MODEL='waffle'
    # or
    export TURTLEBOT3_MODEL='waffle_pi'
    ```

- Launch Gazebo preset:

    ```bash
    roslaunch turtlebot3_gazebo <preset.launch>
    # e.g.
    roslaunch turtlebot3_gazebo turtlebot3_world.launch
    ```

    - Gazebo presets (environments)
    
        |             |                                 |
        |-------------|---------------------------------|
        | Empty World | `turtlebot3_empty_world.launch` |
        | World       | `turtlebot3_world.launch`       |
        | House       | `turtlebot3_house.launch`       |
    
- Drive

    - with teleop:
    
        ```bash
        roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
        ```
    
    - or demo collision avoidance with `turtlebot3_simulation`

        ```bash
        roslaunch turtlebot3_gazebo turtlebot3_simulation.launch
        ```

## Nav and SLAM in simulation

Refers to [Turtlebot3 SLAM](https://emanual.robotis.com/docs/en/platform/turtlebot3/slam/#ros-1-slam) and [Turtlebot3 Navigation](https://emanual.robotis.com/docs/en/platform/turtlebot3/navigation/#ros-1-navigation)


- SLAM 

    - SLAM Method - gmapping
    
        ```bash
        roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
        ```
        
        All methods: gmapping, cartographer, hector, karto, frontier_exploration

    - Save Map
        
        ```bash
        export MAP_FILE=$HOME/projects/dyson-bot/map/map_test
        rosrun map_server map_saver -f $MAP_FILE
        ```

- Navigation

    - Launch Navigation Node
        ```bash
        roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$MAP_FILE.yaml
        ```

