cmake_minimum_required(VERSION 2.8.3)
project(canny_edge_my_face)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  message_generation
  roscpp
  sensor_msgs
  std_msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES canny_edge_my_face
#  CATKIN_DEPENDS roscpp std_msgs
#  DEPENDS system_lib	
   DEPENDS message_runtime
)

###########
## Build ##
###########
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_executable(${PROJECT_NAME}_node src/canny_edge_my_face_node.cpp)

## Specify libraries to link a library or executable target against
target_link_libraries(${PROJECT_NAME}_node
  ${catkin_LIBRARIES}
)
