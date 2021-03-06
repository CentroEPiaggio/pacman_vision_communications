cmake_minimum_required(VERSION 2.8.3)
project(pacman_vision_comm)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  message_generation
  sensor_msgs
  std_msgs
  tf
)
################################################
## Declare ROS messages, services and actions ##
################################################
## Generate messages in the 'msg' folder
add_message_files(
  FILES
  pe.msg
  peArray.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  get_scene.srv
  estimate.srv
  track_object.srv
  grasp_verification.srv
  stop_track.srv
  clusterize.srv
  get_cloud_in_hand.srv
  start_modeler.srv
  stop_modeler_recording.srv
  reset_model.srv
  save_model.srv
)

# Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  geometry_msgs
  sensor_msgs
  std_msgs
)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if you package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES vision_communications
   CATKIN_DEPENDS geometry_msgs message_generation sensor_msgs std_msgs tf
#  DEPENDS system_lib
)

