# Handy Setups

- Appends to `~/.bashrc`

```bash
echo "Sourced ROS melodic from /opt/ros/melodic"
. /opt/ros/melodic/setup.bash
echo "Setting up dysonbot catkin ws"
. ~/projects/dyson-bot/catkin_ws/devel/setup.sh
echo $ROS_PACKAGE_PATH | grep dyson-bot

export TURTLEBOT3_MODEL=burger
```
