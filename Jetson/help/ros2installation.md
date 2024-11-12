# Ros2 installation for ubuntu 22.04

The best way to install it is to follow the steps of the [official ros2 manual](https://docs.ros.org/en/iron/Installation/Ubuntu-Install-Debs.html)

Or use the scritp [ROS2 Humble installation script](ROS2%Humble%installation%script.md)

To check the installation:

**Source ROS 2**: First, make sure your environment is set up by sourcing the ROS 2 setup file:

```
source /opt/ros/humble/setup.bash
```

**Check ROS 2 Installation**: Run the following command to check if ROS 2 commands are recognized:

```
ros2 --help
```
If the command shows a list of ROS 2 options, your installation is likely correct.

#### **Run the Talker and Listener Demo**: 
ROS 2 includes a simple publisher-subscriber demo to test functionality.

In one terminal, start the "talker" (publisher):
```
ros2 run demo_nodes_cpp talker

```
In a second terminal, source the setup file again:
```
source /opt/ros/humble/setup.bash
```
Then start the "listener" (subscriber):
```
ros2 run demo_nodes_cpp listener
```
You should see output in the "listener" terminal showing messages published by the "talker," verifying that communication within ROS 2 is working.




