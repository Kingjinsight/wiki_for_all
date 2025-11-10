## In ROS2

- Before we build, we should source the underlay first, which is the ros humble setup.zsh file
- In the root of the workspace, run `colcon build`. 
```zsh
colcon build --symlink-install
colcon build --packages-up-to
colcon build --event-handlers console_direct+
# --symlink-install allow the installed files to be changed by changing the files in the source space without build again.(e.g. python files or other non-compiled resources, except c++)
# --packages-up-to: builds thie package you want, plus all its dependencies, but not the whole workspace(save time)
# --event-handlers console_direct+ shows console output while building

```

- run test for the packages just built, run 
```zsh
colcon test
```
- when colcon has completed building successfully, the outpt will be in the install directory. We need to source all required elements to our path  before we we can use any of the installed executables or libraries. run 
```zsh
source install/setup.zsh
```
- after all steps above, we can run some nodes
```zsh
ros2 run xxx_subscriber subscriber_function
ros2 run xxx_publisher publisher_function
```
- If you do not want to build a specific package place an empty file named COLCON_IGNORE in the directory

## build python package
1. write source code
2. change setup.py: create command tools, install python library
3. change package.xml: define ros2 dependency like rclpy, std_msgs, tell colcon build type
4. setup.cfg: set installation path 
