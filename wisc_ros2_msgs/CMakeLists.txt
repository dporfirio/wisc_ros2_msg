cmake_minimum_required(VERSION 3.5)

project(wisc_ros2_msgs)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
	add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)

rosidl_generate_interfaces(wisc_ros2_msgs
  "msg/StringArray.msg"
  "msg/TransitionSystems.msg"
  "msg/TransitionSystem.msg"
  "msg/State.msg"
  "msg/Transition.msg"
  "msg/Behavior.msg"
  "msg/Event.msg"
  "msg/Conditional.msg"
)

ament_package()
