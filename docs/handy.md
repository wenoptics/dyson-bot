# Handy Setups

- Appends to `~/.bashrc`

```bash
echo "Sourced ROS melodic from /opt/ros/melodic"
source /opt/ros/melodic/setup.bash
echo "Setting up dysonbot catkin ws"
. ~/projects/dyson-bot/catkin_ws/devel/setup.sh
echo $ROS_PACKAGE_PATH | grep dysonbot

export TURTLEBOT3_MODEL=burger
```
