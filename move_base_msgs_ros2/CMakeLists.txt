cmake_minimum_required(VERSION 3.8)
project(move_base_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

cmake_policy(SET CMP0057 NEW)

# find dependencies
find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

find_package(actionlib_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "action/MoveBase.action"
  "msg/MoveBaseAction.msg"
  "msg/MoveBaseActionFeedback.msg"
  "msg/MoveBaseActionGoal.msg"
  "msg/MoveBaseActionResult.msg"
  "msg/MoveBaseFeedback.msg"
  "msg/MoveBaseGoal.msg"
  "msg/MoveBaseResult.msg"
  DEPENDENCIES actionlib_msgs geometry_msgs std_msgs
 )

ament_package()