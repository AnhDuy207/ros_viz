cmake_minimum_required(VERSION 3.0.2)
project(ros_viz)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  mavros_msgs
  roscpp
  std_msgs
  visualization_msgs
)

catkin_package(
  INCLUDE_DIRS include
#  LIBRARIES ros_viz
  CATKIN_DEPENDS geometry_msgs mavros_msgs roscpp std_msgs visualization_msgs
#  DEPENDS system_lib
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

## Declare a C++ library
# add_library(${PROJECT_NAME}
#   src/${PROJECT_NAME}/ros_viz.cpp
# )
# target_link_libraries(${PROJECT_NAME}
#   ${catkin_LIBRARIES}
# )

add_executable(marker_node src/marker.cpp)

target_link_libraries(marker_node
  ${catkin_LIBRARIES}
)