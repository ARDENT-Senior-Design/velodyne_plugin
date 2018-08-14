velodyne_plugin

Make sure the velodynce_hd132 lidar is cloned into our gazebo model folder: https://github.com/ARDENT-Senior-Design/velodyne_hd132

To run this program:

Open a new terminal and enter the following commands if the package was cloned into the home directory

```
cd ~/velodyne_plugin/build
cmake ../
make
roscore
```

Open another terminal:

```
cd ~/velodyne_plugin/build
export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:~/velodyne_plugin/build
gazebo ../velodyne.world
```

If the speed needs to be changes, publish to the LIDAR's speed:

```
rostopic pub /my_velodyne/vel_cmd std_msgs/Float32 1.0
```

The default speed of the LIDAR is set to 25 rad/s in the velodyne.world file
