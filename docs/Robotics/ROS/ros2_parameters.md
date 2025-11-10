It is a configuration value of a node. You can think of parameters as node settings. A node can store parameters as integers, floats, boolean, strings and lists.

## Basic Commands
```zsh
# =================================================
# Parameters
# =================================================
# list parameters belonging to your nodes
ros2 param list

# display the type and current value of a parameter
ros2 param get <node_name> <parameter_name>

# change a parameter's value at runtime
ros2 param set <node_name> <parameter_name> <value>

# save all of a node's current parameter values into a file
ros2 param dump <node_name>

# load parameters from a file to a currently running node
ros2 param load <node_name> <parameter_file>

# load parameter file on node startup
ros2 run <package_name> <executable_name> --ros-args --params-file <file_name>
```

## Shared parameter for all node
1. use_sim_time
