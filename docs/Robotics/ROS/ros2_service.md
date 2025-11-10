Services are another method of communication for nodes. Services are based on a call-and-response model. While topics allow nodes to subscribe to data streams and get continual updates, services only provide data when they are specifically called by a client.
## Basic Commands
```zsh
# =================================================
# Service
# =================================================
# list all the services currently active in the system
ros2 service list <-t>
# -t option allow us to list all service that contain service type

# find out the type of a service
ros2 service type <serivce_name>

# if you want to find all the services of a specific type
ros service find <type_name>

# can call services from the command line, but we need to know the structure of the input arguments
ros2 interface show <type_name>.srv
# THe --- separates the request structure(above) from the response structure(below).

# call a service 
ros2 service call <service_name> <service_type> <arguments>
```

## Create a service
1. init
	1. inherit Node and name it
	2. create service(service type, name, callback)
2. define callback

## Create a client
1. init
	1. inherit Node and name it
	2. the type and name must match for the client and service to be able to communicate
	3. while loop in the constructor checks if a service matching the type and name of the client is available once a second.
	4. Create a new request object
	5. define send request method
2. main
	1. init rclpy
	2. construct object
	3. send request
	4. spin_until_future_complete
	5. log resultx


## Create custom msg and srv files
1. create a new package
2. mkdir msg srv
3. msg definition
4. srv definition
5. change Cmakelist.txt
6. add dependency in package.xml
7. build

