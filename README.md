# pandar40p_ros

## Build
```
mkdir -p rosworkspace/src
cd rosworkspace/src
git clone https://github.com/HesaiTechnology/Pandar40p_ros.git --recursive
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
/pandar40p/sensor/pandar40p/hesai40/PointCloud2
```
