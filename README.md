# Pandora_ros

## Build
```
mkdir -p rosworkspace/src
cd rosworkspace/src
git clone https://github.com/HesaiTechnology/Pandora_ros.git
cd ..
catkin_make
```

## Run
```
source devel/setup.sh
roslaunch pandora pandora_driver.launch


## ROS Topic name
```
/PointCloud2
/front_color
/front_gray
/right_gray
/back_gray
/left_gray
```

