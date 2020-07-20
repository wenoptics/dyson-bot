

## Setup ROS env

```bash
echo "Sourced ROS melodic from /opt/ros/melodic"
source /opt/ros/melodic/setup.bash
```

## ROS Filesystem Commands

- `rospack`

    - e.g. `rospack profile` - Update the registered packages

- `roscd <pkg>[/deep/path]`

- `rosls <pkg>`


## Catkin 

FS Structure

    catkin_ws/
    ├── build/                              # Build space
    │   └── ... 
    ├── devel/                              # Development space
    │   ├── ...
    │   └── setup.sh
    └── src/                                # Source space
        ├── package1_name/
        │   ├── CMakeLists.txt
        │   └── package.xml
        ├── package2_name/
        ├── ...
        └── CMakeLists.txt 

### (once-for-good) Initialize catkin workspace

```bash
mkdir -p catkin_ws/src

cd catkin_ws/src
catkin_init_workspace

cd catkin_ws
catkin_make
```


### Setup catkin workspace

```bash
echo "Setting up dysonbot catkin ws"
. catkin_ws/devel/setup.sh
echo $ROS_PACKAGE_PATH | grep `pwd`
```


### Create a package (`catkin_create_pkg`)

```bash
cd catkin_ws/src
catkin_create_pkg <pkg-name> [dep1] [dep2] [...]
```

e.g. 

```bash
catkin_create_pkg beginner_tutorials std_msgs rospy roscpp
```

### Build a Pacakge(`catkin_make`)

```bash
cd <catkin-ws>
catkin_make
```

Use `--force-cmake` if you add new packages inside the workspace:

```bash
cd <catkin-ws>
catkin_make --force-cmake
```

## ROS Shell Commands

- `rosnode` e.g. 

  - `rosnode info <node-name>`
   
  - `rosnode list`

  - `rosnode ping`

  - `rosnode kill`

- `rostopic` - sub-pub mechanism. e.g.

  - `rostopic list [-v]`

  - `rostopic echo <topic-name>`

- `rosmsg`, (.msg) message is the type of the topic e.g.,

  - `rostopic type <topic-name>` -> msg-name

  - `rosmsg show <msg-name>`

- `rosservice` - request/response machanism

  - `rosservice list`

- `rossrv`, (.srv) srv is the type of the service

  - `rosservice type <service-name>` -> srv-name

  - `rossrv show <srv-name>`

## Refs

- [ROS Tutorial](https://wiki.ros.org/cn/ROS/Tutorials)

- [Turtlebot 3](https://github.com/ROBOTIS-GIT/turtlebot3)
