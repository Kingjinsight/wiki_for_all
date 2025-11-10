Actions are one of the communication types in ROS2 and are intended for long running tasks. They consist of three parts: a goal, feedback and a result

Actions are built on [topics](ros2_topics.md) and [services](ros2_services.md). Their functionality is similar to services, except actions are preemptable. They also provide steady feedback, as opposed to services which return a single response.

Actions use a client-server model. An "action client" node sends a goal to an "action server" node that acknowledges the goal and returns a stream of feedback and a result

### Very similar to Topic + Service, continuous data, waiting for response, can be cancel, feedback for progress


## Basic commands
```zsh
# Identify all the actions in the ROS graph
ros2 action list <-t>
# <-t> option shows all actions's action type

# infomation about action detail, action clients, action servers
ros2 action info <action_name>

# show structure of the action type
ros2 interface show <action_type>
# The sction of this message above thei first --- is the structure(data type and name) of the goal request. The next section is the structure of teh result. The last section is the structure of the feedback.

# send an action goal
ros2 action send_goal <action_name> <action_type> <values> <--feedback>
# <value > in YAML format
# <--feedback> will see th feedback of this goal
```
