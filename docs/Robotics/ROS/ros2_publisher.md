## Createa a publisher
1. Init
	1. inherit from parent
	2. define messages of publisher node(data type, topic name, queue size)
		- queue size: It's the number of message that will help subscriber to hold  if subscribe received message slowly, rather than control the sending speed
	3. set a timer, used to control sending speed
	4. set a counter self.i used in callback
2. set timer_callback
	1. it creates a message with the counter value appended, and publishes it to the console with get_logger().info
3. set main function
	1. rclpy.init(args=args)
	2. define node in a variable
	3. called rclpy.spin(node) to repeattedly called timer_callback until type ctrl+c the loop then close
	4. (optional) publisher.destroy_node()
	5. rclpy.shotdown()
4. Add dependency in setup.py, setup.cfg and package.xml
