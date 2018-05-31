cmake_minimum_required(VERSION 2.8.3)
project(pandar40p)
find_package(catkin REQUIRED)
catkin_package(
    CATKIN_DEPENDS)

find_package(catkin REQUIRED COMPONENTS
    image_transport
    roscpp
    roslib
    sensor_msgs
)

find_package( Boost REQUIRED )
find_package( PCL REQUIRED COMPONENTS common )

catkin_package()
set (CMAKE_CXX_FLAGS "-fPIC --std=c++11")

add_subdirectory(src/Pandar40P)

include_directories(
    .
    src/Pandar40P/src/Pandar40P/include
    src/Pandar40P/include
    ${Boost_INCLUDE_DIRS}
    ${PCL_INCLUDE_DIRS}
    ${catkin_INCLUDE_DIRS}
)

add_executable(pandar40p_node
    src/main.cc
)

target_link_libraries(pandar40p_node
    Pandar40PSDK
    ${catkin_LIBRARIES}
)

install(DIRECTORY include/
        DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION})
install(DIRECTORY launch/
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch)
install(TARGETS pandar40p_node
        RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
