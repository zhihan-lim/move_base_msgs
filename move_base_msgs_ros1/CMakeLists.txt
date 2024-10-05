cmake_minimum_required(VERSION 3.0.2)
project(move_base_msgs)

## Compile as C++11, supported in ROS Kinetic and newer
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  actionlib_msgs
  message_generation
  message_runtime
  nav_msgs
  std_msgs
)

# Generate messages in the 'msg' folder
add_message_files(
  FILES
    MoveBaseAction.msg
    MoveBaseActionFeedback.msg
    MoveBaseActionGoal.msg
    MoveBaseActionResult.msg
    MoveBaseFeedback.msg
    MoveBaseGoal.msg
    MoveBaseResult.msg
)

# Generate actions in the 'action' folder
add_action_files(
  FILES
    MoveBase.action
)
# Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
    actionlib_msgs
    nav_msgs
    std_msgs
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
)
