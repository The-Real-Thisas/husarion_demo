# Husarion Demo

This repository contains a demo package with three examples for the Husarion platform.

## Installation

### Prerequisites

This demo requires the following packages to be installed:
- `astra_camera`
- `gmapping`
- `rviz`

### Installing the `husarion_demo` package

To install the `husarion_demo` package, clone this repository into your workspace and build it:

    ```
    cd ~/ros_workspace/src
    git clone
    cd ..
    catkin_make
    ```

## Examples

### Camera Demo

This example shows how to get image topics from `astra_camera` package. It opens two `image_view` windows with color and depth images.

Launch the `cam_demo` example by running the following command:
    
    ```
    roslaunch husarion_demo cam_demo.launch
    ```

### Odometry Demo

This example shows how to get odometry data. It prints the data from `/odom` topic. It opens `rviz` window with the robot model and camera feeds. 

This example requires the rosbot and ros-master containers to be running. To run them, run the following command:

    ```
    docker compose up -d rosbot ros-master
    ```

Launch the `simple` example by running the following command:
    
    ```
    roslaunch husarion_demo simple.launch
    ```

### SLAM Demo

This example shows how to run `gmapping` SLAM package. It opens `rviz` window with the robot model and camera feeds along with map and laser scan data from `gmapping`.

This example requires the rosbot, ros-master & rplidar containers to be running. To run them, run the following command:

    ```
    docker compose up -d rosbot ros-master rplidar
    ```

Launch the `slam` example by running the following command:
    
    ```
    roslaunch husarion_demo slam.launch
    ```

## Troubleshooting

### No data from `/odom` topic

If you don't see any data from `/odom` topic when you run `rostopic echo /odom`, you may need to reflash the firmware on your rosbot.

To do so run the following:

    ```
    ./flash_firmware.sh
    ```

A copy of this file is included in this repository.

### Astra camera not working

If the `astra_camera` package does not work it is recommended to reinstall the package and follow the instructions on the repository page:

https://github.com/orbbec/ros_astra_camera