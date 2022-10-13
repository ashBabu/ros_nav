### Step by step instructions to ROS Navigation stack
Setup your catkin workspace
* `mkdir -p skidy_ws/src`
* `cd skidy_ws/src`
* `git clone https://github.com/ashBabu/ros_nav.git`
* `cd ../../`
* `catkin_make`
* `source devel/setup.bash`


`skidy_1_basic.urdf` is the very basic urdf with links and joints for a mobile robot. To view the urdf,
* `sudo apt-get install ros-melodic-urdf-tutorial`
* `roslaunch urdf_tutorial display.launch model:='$(find ros_nav)/urdf/skidy_1_basic.urdf'`

<img style="float: left;" title="skidy basic" src="images/skidy_1_basic.png" alt="spacecraftRobot" width="800" height="400"/>


The above figure shows the Rviz with the skidy_1_basic.urdf.

### Creating a gazebo world
Official tutorial available [here](https://classic.gazebosim.org/tutorials?tut=build_world&ver=1.9).

Fire up a terminal and type the following
* `gazebo`  
this will launch the an `empty_world` in `gazebo`. Add primitives (sphere, cuboid etc.) or use the `Insert` tab to create your own world. Save your world under `ros_nav/gazebo_worlds/simple_world.world`.
* `roslaunch ros_nav gazebo_world.launch` # to launch this

### Spawn skidy in gazebo
This requires adding the following to the `gazebo_1_world.launch` and is given in `gazebo_2_skidy.launch`

`<node name="spawn_urdf" pkg="gazebo_ros" type="spawn_model" args="-file $(find ros_nav)/urdf/skidy_1_basic.urdf -urdf -z 1 -model skidy_bot" />`

This will look as shown below

<img style="float: left;" title="skidy basic" src="images/gazebo_skidy_world.png" alt="spacecraftRobot" width="800" height="400"/>
