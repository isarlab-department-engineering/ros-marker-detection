cmake_minimum_required(VERSION 2.8.3)
project(aruco_detection)


find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  cv_bridge
  message_generation
)
find_package(OpenCV 3.2 EXACT REQUIRED)

## System dependencies are found with CMake's conventions
# find_package(Boost REQUIRED COMPONENTS system)



## Generate messages in the 'msg' folder
add_message_files(
   FILES
   ArMarkers.msg
#  Message2.msg
)

## Generate services in the 'srv' folder
# add_service_files(
#   FILES
#   Service1.srv
#   Service2.srv
# )

## Generate actions in the 'action' folder
# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

## Generate added messages and services with any dependencies listed here
generate_messages(
   DEPENDENCIES
   std_msgs
)




catkin_package(
	CATKIN_DEPENDS message_runtime
)

include_directories(include 
	${catkin_INCLUDE_DIRS}
	${OpenCV_INCLUDE_DIRS}
)


## Declare a C++ library
# add_library(aruco_detection
#   src/${PROJECT_NAME}/aruco_detection.cpp
# )

## Add cmake target dependencies of the library
## as an example, code may need to be generated before libraries
## either from message generation or dynamic reconfigure
# add_dependencies(aruco_detection ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

##
## Declare a C++ executable
##
add_executable(aruco_detector src/aruco_detector.cpp)
target_link_libraries(aruco_detector
	${catkin_LIBRARIES}
	${OpenCV_LIBRARIES}
)



##add_executable(listener src/listener.cpp)
##target_link_libraries(listenOpenCV_DIRer ${catkin_LIBRARIES})
##add_dependencies(listener beginner_tutorials_generate_messages_cpp)




## Add cmake target dependencies of the executable
## same as for the library above
# add_dependencies(aruco_detection_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

add_dependencies(aruco_detector aruco_detection_generate_messages_cpp)
