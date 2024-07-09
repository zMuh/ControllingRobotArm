# Controlling Robot Arm

### 1 - Creating workspace

Create a folder:
```bash
mkdir -p ~/catkin_ws/src
```

Navigate to the workspace:
```bash
cd ~/catkin_ws
```

Build the workspace:
```bash
catkin_make
```

Add workspace setup to `bashrc`:
```bash
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
```

### 2 - Installing packages

Clone the package from GitHub into `src`:
```bash
cd ~/catkin_ws/src
git clone https://github.com/smart-methods/arduino_robot_arm
```

Navigate back to `catkin_ws`:
```bash
cd ~/catkin_ws
```

Install dependencies in `catkin_ws`:
```bash
rosdep install --from-paths src --ignore-src -r -y
sudo apt-get install ros-noetic-moveit
sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
sudo apt-get install ros-noetic-gazebo-ros-control ros-noetic-ros-controllers ros-noetic-ros-control
```

### 3 - Compiling the package

Compile the package:
```bash
catkin_make
```

### 4 - Controlling the arm

Launch the arm control simulation:
```bash
roslaunch robot_arm_pkg check_motors.launch
```

![photo](https://img001.prntscr.com/file/img001/XRdLtqHNT5-TTL5PvJCCpQ.png)

This will start the simulation and display a GUI named `joint_state_publisher` which is used to control arm movements.

![photo](https://img001.prntscr.com/file/img001/UmW2yp98T7qEysZKRU86uw.png)

You can adjust the joint angles here and reset them to their initial values using the center button.
