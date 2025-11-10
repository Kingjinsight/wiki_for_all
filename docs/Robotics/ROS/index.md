# Basic Concepts
- [RQT](RQT.md)
- [ROS2 Node](ros2_node.md)
- [ROS2 topics](ros2_topics.md)
- [ROS2 publisher](ros2_publisher.md)
- [ROS2 subscriber](ros2_subscriber.md)
- [ROS2 service](ros2_service.md)
- [ROS2 actions](ros2_actions.md)
- [ROS2 parameters]( ros2_parameters.md)
- [Colcon](colcon.md)


## Publisher--subscriber-topic model
1. **1** publisher can send message to only **1** topic, since each topic receive only one message type
2. **1** node can have **multiple** publishers, and send to different topics
3. **1** topic can have **multiple** publishers and subscribers
4. all message send to one topic should be the same message type


## Call-response-service model
1. **1** server can support **multiple** services
2. **1** client can call **multiple** services
3. **1** service can only have **1** server
4. **1** service can have **multiple** clients


## Difference between topic and service
topics allow node to subscribe to data streams and get continual updates, services only provide data when they are specifically called by a client

 
| Topic              | Service                    |
| ------------------ | -------------------------- |
| Sensor streaming   | One-time operation         |
| Status information | Computation task           |
| Control command    | Config and setting         |
| log                | Execute an action sequence |

## Logger levels
- Fatal: indicate the system is going to terminate to try to protect itself from detriment
- Error: indicate significant issues that won't necessarily damage the system, but are preventing it from functioning properly
- warn: indicate unexpected activity or non-ideal results that might represent a deeper issue, but don't harm functionality outright
- info: indicate event and status updates that serve as a visual verification that the system is running as expected
- debug: detail the entire step-by-step process of the system execution
- how to use 
	- set to debug -> display all logs
	- set to info -> display info, warn, error, fatal
	- set to warn -> display warn, error, fatal
	- Developing stage: debug
	- Testing stage: info
	- Production stage: warn

## Launching nodes
allow you to start up and configure a number of executables containing ROS 2 node simultaneously. Running a single launch file with the `ros2 launch` command will start up your entire system - all nodes and their configurations - at once.

## Recording and playing back data
the data will be accumulated in a new bag directory with a name in the pattern of `rosbag2_year_month_day_hour_minute_second`. This dirctory will contain a `metadata.yaml`
```zsh
# record data published to a topic
ros2 bag record <topic_name>

# record multiple topics
ros2 bag record -o subset /turtle1/cmd_vel /turtle1/pose
# -o options allows you to choos a unique name for your bag file
# to record more than one topic at at ime, simply list each topic separated by a space

# see details about your recording
ros2 bag info <bag_file_name>
```

Before replaying the bag file, enter ctrl+c in the terminal where the teleop is running. Then make sure your turtlesim window is visible so you can see the bag file is action.

```zsh
ros2 bag play <bagi_file_name>
```

## Workspace
- Subdirectory
	- src: It is where the source code of ROS packages will be located
	- build: create by colcon, where intermediate files are stored. For each package a subfolder will be created in which e.g. CMake is being invoked
	- install: It is where each packages will be installed to. By default each package will be installed into a separate subdirectory
	- log: It contains various logging information about each colcon invocation.
- underlay: 
- Create the workspace
	- before building the workspace, you need to resolve the package dependencies, from the root of your workspace  
        ```
        rosdep install -i --from-path srsc --rosdistro humble -y
        ```
	- source underlay
	- source overlay in the root
        ```
        source install/local_setup.zsh
        ```


## Package
- A package is an organizational unit for your ROS2 Code. Used to share with others, and you can release your ROS2 work and allow others to build and use it easily.
- Minimum required contents
	- CMake
		- CMakeLists.txt
		- include/<package_name>
		- package.xn=ml
		- src
	- Python
		- package.xml
		- resource/\<package_name>
		- setup.cfg
		- setup.py
		- <packagename>

```zsh
ros2 pkg create --build-type ament-python --license Apache-2.0 --node name  <package name> <node name> -- dependencies <dependency-name>
```
- Content inside package.xml and setup.py shoule be the same.


## Ament
It is a build system and packaging tool, designed to replace ROS1's catkin, think it as a specialized "compiler and package manager" for ROS 2.
Ament toolset:
1. ament_cmake
2. ament_python
3. ...
