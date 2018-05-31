# pandar40p_ros

## Build
```
mkdir -p rosworkspace/src
cd rosworkspace/src
git clone https://github.com/HesaiTechnology/pandar_ros.git
cd ..
catkin_make
```

## Run
```
source devel/setup.sh
roslaunch pandar pandar40p_driver.launch
```

## ROS Topic name
```
/PointCloud2
```
