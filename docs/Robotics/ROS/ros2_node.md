1. Each node responsible for a single modular purpose
2. Each node can send and receive data from other nodes via [topics](ros2_topics.md), [service](ros2_services.md), [actions](ros2_actions.md), or [parameters](ros2_parameters.md)
3. a single executable can contain one or more nodes.
## Basic Commands
```zsh
# =================================================
# Node
# =================================================
# launch an executable from a package
ros2 run <package_name> <executable_name>

# list all nodes' name
ros2 node list

# reassign default node properties, like node name, topic names
ros2 run turtlesim turtlesim_node --ros-args --remap __node:=my_turtle

# access more information(publisher, subscriber, service, action) about node
ros2 node info <node_name>
```
