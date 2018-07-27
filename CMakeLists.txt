cmake_minimum_required(VERSION 2.8.3)
project(pandora)
find_package(catkin REQUIRED)
catkin_package(
    CATKIN_DEPENDS)

find_package(catkin REQUIRED COMPONENTS
    cv_bridge
    image_transport
    roscpp
    roslib
    sensor_msgs
)

find_package( Boost REQUIRED )
find_package( PCL REQUIRED COMPONENTS common )
find_package( OpenCV REQUIRED )

catkin_package()
set (CMAKE_CXX_FLAGS "-fPIC --std=c++11")

add_subdirectory(src/pandora)

include_directories(
    .
    src/pandora/include
    src/pandora/src/Pandar40P/include
    ${Boost_INCLUDE_DIRS}
    ${PCL_INCLUDE_DIRS}
    ${OpenCV_INCLUDE_DIRS}
    ${catkin_INCLUDE_DIRS}
)

add_executable(pandora_node
    src/main.cc
)

target_link_libraries(pandora_node
    Pandora
    ${OpenCV_LIBS}
    ${catkin_LIBRARIES}
)
install(DIRECTORY launch/
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch)
install(TARGETS pandora_node
        RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

