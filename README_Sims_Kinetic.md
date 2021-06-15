# Simulations of the robots - Kinetic

## Robot 1: Fetch

we can use the **construct's one**

```
cd ~/catkin_ws/src 
git clone https://ncbdrck@bitbucket.org/theconstructcore/fetch_tc.git
```

### Addtional packages we need
```
# Install the offical one to install most of the deps
sudo apt-get update
sudo apt-get install ros-$ROS_DISTRO-fetch-gazebo-demo
sudo apt-get install ros-kinetic-teleop-twist-keyboard

# then the ros packages we need 
cd catkin_ws/src
git clone https://ncbdrck@bitbucket.org/theconstructcore/spawn_robot_tools.git
git clone https://github.com/mikeferguson/simple_grasping.git
cd ..
rosdep install --from-paths src --ignore-src -r -y
catkin_make
source devel/setup.bash

# only if you are getting errors
cd ~/catkin_ws/src
git clone https://github.com/mikeferguson/robot_calibration.git
git clone https://github.com/mikeferguson/code_coverage.git
cd ..
rosdep install --from-paths src --ignore-src -r -y
catkin_make
source devel/setup.bash
```

### additional information (Optional) - we do not need to install these if we are using the construct's one

let's start with the official version of the Fetch robot

- http://docs.fetchrobotics.com/gazebo.html

or this one 

- https://github.com/fetchrobotics/fetch_gazebo

**this will remove most of the errors if you have**

This one I copied from the Construct Openai with ros course- not needed
```
git clone https://github.com/ncbdrck/fetch_tc.git
```





## Robot 2: ABB Robot

first we need to install ROS industrial
- http://wiki.ros.org/Industrial/Install

```
sudo apt-get install ros-kinetic-industrial-core
sudo apt-get install ros-kinetic-abb
sudo apt-get install ros-kinetic-ros-canopen
```


we can get the robot we have on the lab from the **"abb_experimental"** repo
- https://github.com/ros-industrial/abb_experimental

```
# change to the root of the Catkin workspace
cd $HOME/catkin_ws

# retrieve the latest development version of the abb repository. If you'd rather
# use the latest released version, replace 'kinetic-devel' with 'kinetic'
git clone -b kinetic https://github.com/ros-industrial/abb.git src/abb
# retrieve the latest development version of abb_experimental
git clone -b kinetic-devel https://github.com/ros-industrial/abb_experimental.git src/abb_experimental

# check build dependencies. Note: this may install additional packages,
# depending on the software installed on the machine
rosdep update

# be sure to change 'kinetic' to whichever ROS release you are using
rosdep install --from-paths src/ --ignore-src --rosdistro kinetic

# build the workspace (using catkin_tools) 
# Only do this if all the dependencies are correctly installed. Otherwise, refer to the below section to install dependencies
catkin_make
```

### Additional packages and dependencies they might ask (Only install if asked)

you might get moveit dependencies errors

- http://docs.ros.org/en/kinetic/api/moveit_tutorials/html/doc/trac_ik/trac_ik_tutorial.html

```
sudo apt-get install ros-kinetic-trac-ik-kinematics-plugin
cd $HOME/catkin_ws
rosdep install --from-paths src --ignore-src -r -y
```



Then we need to install the ABB driver (only if they asked)
**Usually, this will be installed automatically when we install ros-industrial/abb**

- https://github.com/ros-industrial/abb_driver


you can install it using the apt (recommended)
```
sudo apt install ros-kinetic-abb-driver
```
or from the source

```
# change to the root of the Catkin workspace
cd $HOME/catkin_ws

# retrieve the latest development version of the abb_driver repository. If you'd rather
# use the latest released version, replace 'kinetic-devel' with 'kinetic'
git clone -b kinetic https://github.com/ros-industrial/abb_driver.git src/abb_driver

# check for and install missing build dependencies.

# first: update the local database
rosdep update

# now install dependencies, again using rosdep.
# Note: this may install additional packages, depending on the software already present
# on the machine.
# Be sure to change 'kinetic' to whichever ROS version you are using
rosdep install --from-paths src/ --ignore-src --rosdistro kinetic

# build the workspace (using catkin_tools)
catkin_make
```

additional links we may need later
- http://wiki.ros.org/action/show/abb_driver/Tutorials?action=show&redirect=abb%2FTutorials









## Robot 3: iri_wam

we can use the **construct's one**

```
git clone -b noetic https://ncbdrck@bitbucket.org/theconstructcore/iri_wam.git
```

### Addtional packages we need
```
cd catkin_ws/src
git clone https://ncbdrck@bitbucket.org/theconstructcore/hokuyo_model.git
cd ..
rosdep install --from-paths src --ignore-src -r -y
catkin_make
source devel/setup.bash
```



