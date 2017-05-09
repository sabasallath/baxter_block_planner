# baxter_block_planner
Ros - Gazebo - Baxter blocks problem solving

# Installation

## pre-requisite : ros, gazebo, baxter-sdk

- Follow instruction at : https://github.com/sabasallath/baxter

## pre-requisite : java 8

- Follow instruction at : http://ubuntuhandbook.org/index.php/2015/01/install-openjdk-8-ubuntu-14-04-12-04-lts/

## pre-requisite : move-it

- Follow instruction at : http://sdk.rethinkrobotics.com/wiki/MoveIt_Tutorial

    **/!\ REBOOT after MoveIt installation**

    If still in trouble :

    ```
    cd ~/ros_ws/
    rm -rf build/
    rm -rf devel/
    catkin_make
    catkin_make install
    ```

# Baxter block package installation

- Clone sabasallath/baxter_block_planner.git in ~/ros_ws/src/

    ```
    git clone https://github.com/sabasallath/baxter_block_planner.git
    ```
    
- In ~/ros_ws directory :
    
    ```
    catkin_make
    catkin_make install
    ```

## run it

- In a first terminal do
    
    ```
    cd ~/ros_ws/
    ./baxter.sh sim
    roslaunch baxter_block_planner block_planner.launch
    ```

- Wait until this message (**If gazebo crash : exit terminal and try again !**):
    ```
    [ INFO] [xxxxxxxxxx.xxxxxxxxx, xxxxxxxxxxxx] Gravity compensation was turned on
    ```
    
- In a second terminal do

    ```
    cd ~/ros_ws/
    ./baxter.sh sim
    rosrun baxter_block_planner block_planner.py
    ```
    
# Current state of the project

- Can solve problem p01.pddl 
and any problem with an initial situation where all the block are on the table (up to 8 blocks).
- Generate, Delete, Pick and Place blocks with fixed position.

## Todo

- Parse problem definition to set up appropriate initial situation.
- Fix block mass, inertial value.
- Locate blocks positions with sensors.