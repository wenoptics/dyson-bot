
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
