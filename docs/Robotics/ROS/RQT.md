RQT is a graphical user interface (GUI) framework for ROS (Robot Operating System) that provides a centralized environment for running various tools and interfaces as plugins

## Basic commands
```zsh
# run rqt
rqt

# start rqt_console
ros2 run rqt_console rqt_console

```

## rqt_console
It is used to introspect log messages in ROS2.
It has three sections
- The first section of the console is where log messages from your system will display
- In the middle you have the option to filter messages by excluding severity levels. You can also also add more exclusion filters using the plus-sign button to the right
- The button section is for highlighting messages that include a string you input
