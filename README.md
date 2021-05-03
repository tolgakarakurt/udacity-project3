# udacity-project3
### Udacity's nano degree program: Robotics Software Engineering  
**Project Title**: Where Am I?  
**Project Goals**: 
- Robot Localizaton using Adaptive Monte Carlo Localization Algorithms..

### Requirements:
#### Dependencies:
```
$ sudo apt-get install ros-kinetic-navigation
$ sudo apt-get install ros-kinetic-map-server
$ sudo apt-get install ros-kinetic-move-base
$ sudo apt-get install ros-kinetic-amcl
```
- Install libignition-mat2-dev, protobuf-compiler
  - `sudo apt-get install libignition-math2-dev protobuf-compiler`
  - 

### Action
- Open terminal
  - `$ source devel/setup.bash`
  - `$ GAZEBO_PLUGIN_PATH=PATH/TO/collision_map_creator_plugin/build/ gazebo src/pgm_map_creator/world/<yourworld>.world`
 
- Open a new terminal
  - `gzserver src/pgm_map_creator/world/<yourworld>.world`

- Open another terminal
  - `roslaunch pgm_map_creator request_publisher.launch`

- Map will be generated under `/src/pgm_map_creator/maps`
  - If needed, you can adjust the image boundaries (xmin, xmax, ymin, ymax) by editing `src/pgm_map_creator/launch/request_publisher.launch` as shown below:
```
<launch>
  <arg name="map_name" default="map" />
  <arg name="save_folder" default="$(find pgm_map_creator)/maps" />
  <arg name="xmin" default="-20" />
  <arg name="xmax" default="20" />
  <arg name="ymin" default="-20" />
  <arg name="ymax" default="20" />
  <arg name="scan_height" default="5" />
  <arg name="resolution" default="0.01" />
  ...
  ```