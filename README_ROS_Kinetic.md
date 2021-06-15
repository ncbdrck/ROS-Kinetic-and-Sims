# Lets Start with ROS install

# For Kinetic
To install ROS **kinetic** we need **Ubuntu 16**. It doesn't work with the newest version.

## Step 1: Ubuntu 16

- https://releases.ubuntu.com/16.04/


## Step 2: Install ROS kinetic

**Official**
- http://wiki.ros.org/kinetic/Installation/Ubuntu

**or alternative guide** 

- https://roboticslab-uc3m.github.io/installation-guides/install-ros.html


## Step 3: Creating a workspace for catkin

- http://wiki.ros.org/catkin/Tutorials/create_a_workspace

```
# IF you are getting an error when you catkin_make for the first time use this
catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python2
```

## Step 4: How to add to env variables

**Remember to use the username form "jay" to yours in the below code**
```
echo "source /home/jay/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

### Step 5: ROS contols
```
sudo apt-get install ros-kinetic-ros-control ros-kinetic-ros-controllers
```

#### Step 6: Moveit
```
sudo apt-get install ros-kinetic-moveit
```

#### Step 7: Navigation
```
sudo apt-get install ros-kinetic-navigation
```

#### Step 8: Installing ROS perception
```
sudo apt-get install ros-kinetic-perception
```

#### Step 9: Install gazebo_ros_pkgs
```
sudo apt-get install ros-kinetic-gazebo-ros-pkgs ros-kinetic-gazebo-ros-control
```
#### Step 10: Install this package to run multiple instances of the gazebo simulators
```
sudo apt-get install ros-kinetic-multimaster-fkie
rosdep update
```

#### Step 11: Get nessesary dependencies
```
rosdep install --from-paths src --ignore-src -r -y


or 

rosdep install --from-paths src --ignore-src --rosdistro kinetic -y -r
```
### Step 12: Sudo update
```
sudo apt-get update
```

## Step 13: Installing pip for Python 2
```
# refreshing the repositories
sudo apt update
# its wise to keep the system up to date!
# you can skip the following line if you not
# want to update all your software
sudo apt upgrade
# installing python 2.7 and pip for it
sudo apt install python2.7 python-pip
```

If you want to install any package for python 2.7
```
pip2 install <package>
```
**Do nto use the code "pip" with python2. We need to use "pip2". "pip" is for python3**

## Step 13: Select Python 2

Here, we have to change the default python version to **python2**. When we install ROS kinetic, it will automatically install both Python2 and Python3. However, we need **python2** for **ROS kinetic**. It does not work with python3. So we need to change it to always work with python2.  

- https://www.fosslinux.com/39384/switching-between-python-2-and-3-versions-on-ubuntu-20-04.htm

## Step 15: OpenAi_Ros (For Reinforcement Learning with ROS)

```
cd ~/catkin_ws/src
git clone https://bitbucket.org/theconstructcore/openai_ros.git
git clone https://ncbdrck@bitbucket.org/theconstructcore/theconstruct_msgs.git
pip install grpcio-gcp
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src -r -y
catkin_make
source devel/setup.bash
rosdep install openai_ros
```


