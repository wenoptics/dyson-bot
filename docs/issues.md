## python module `empy` missing

Make sure

```bash
pip uninstall em
pip install empy
```

If issue persist, you may also re-create a new catkin ws ([ref](https://answers.ros.org/question/257331/python-module-empy-missing-tutorials/))


1. source ros from /opt/ros/<distro>/setup.bash

2. clean up your catkin workspace (except src)

```bash
cd ~/catkin_ws
unlink src/CMakeLists.txt
rm -rf build
rm -rf devel
rm .catkin_workspace
```

3. re-initialize the workspace with `catkin_init_workspace` from inside src

4. `catkin_make`
