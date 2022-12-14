# setup-system
version : 18.04

source : ROBOTIS e-manual, turtlebot3

https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/

## Install ROS on PC
    sudo apt-get update
    
    sudo apt-get upgrade

    wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh
    
    chmod 755 ./install_ros_melodic.sh 
    
    bash ./install_ros_melodic.sh

## Install Dependent ROS Packages
    sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
    ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
    ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
    ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
    ros-melodic-rosserial-server ros-melodic-rosserial-client \
    ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
    ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
    ros-melodic-compressed-image-transport ros-melodic-rqt* \
    ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers

## Install TurtleBot3 Packages (optional)
    sudo apt-get install ros-melodic-dynamixel-sdk
    
    sudo apt-get install ros-melodic-turtlebot3-msgs
    
    sudo apt-get install ros-melodic-turtlebot3
    
## Install Simulation Package
    cd ~/catkin_ws/src/
    
    git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
    
    cd ~/catkin_ws && catkin_make
    
## Install a Jetson board on a Jackal
    cd src
    
    git clone https://github.com/jackal/jackal
    
    git clone https://github.com/jackal/jackal_desktop.git
    
    cd ..
    
    rosdep install --from-paths src --ignore-src -r -y
    
    catkin_make
    
    source devel/setup.bash
