1. Act as a bus for node to exchange messages
2. a node may publish data to any number of topics and simultaneously have subscriptions to any number of topics

## topic type
how nodes know they're talking about the same information as it moves over topics

## Basic Commands
```zsh
# =================================================
# Topic
# =================================================
# list all topics currently active in the system
ros2 topic list <-t>
# -t option allow us to list all topic that contain topic type

# See the data being published on topic
ros2 topic echo <topic_name>

# See topic information
ros2 tokpic info /turtle1/cmd_vel

# IF you have the mesage structure, you can publish data onto a topic directly
ros2 topic pub <--once/--rate 1> <topic_name> <msg_type> '<args>'
#<--once> option means publish one message then exit
#<--rate 1> option means publish the command in a steady stream at 1hz

# view the rate at which data is published using
ros2 topic hz <topic_name>

```

## How to create publisher-subscriber stystem
[publisher](ros2_publisher.md)
[subscriber](ros2_subscriber.md)
