# Pandora_ros

## Build
```
mkdir -p rosworkspace/src
cd rosworkspace/src
git clone https://github.com/HesaiTechnology/Pandora_ros.git --recursive
cd ..
catkin_make
```

## Run
```
source devel/setup.sh
roslaunch pandora pandora_driver.launch
```

## ROS Topic name
```
/pandora/sensor/pandora/hesai40/PointCloud2
/pandora/sensor/pandora/camera/front_color
/pandora/sensor/pandora/camera/front_gray
/pandora/sensor/pandora/camera/right_gray
/pandora/sensor/pandora/camera/back_gray
/pandora/sensor/pandora/camera/left_gray
```
