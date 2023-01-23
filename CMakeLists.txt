cmake_minimum_required(VERSION 3.8)
project(cpp_pubsub)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake_auto REQUIRED)

# find_package(ament_cmake_auto REQUIRED)
# find_package(rclcpp REQUIRED)
# find_package(std_msgs REQUIRED)
# finx_package()は一行にまとめられる
ament_auto_find_build_dependencies()


ament_auto_add_executable(talker 
src/publisher_member_function.cpp)

# target_include_directories(talker PUBLIC
# $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
# $<INSTALL_INTERFACE:include>)
# target_include_directories(cpp_pubsub PUBLIC
#   include
# )

# ament_auto_add_library(talker SHARED
#  src/publisher_member_function.cpp include/minimal_publisher.hpp)

# ament_auto_add_executable(talker 
# src/publisher_member_function.cpp
# )

# add_executable(talker src/publisher_member_function.cpp)

# # https://docs.ros.org/en/foxy/How-To-Guides/Ament-CMake-Documentation.html

# ament_target_dependencies(talker rclcpp std_msgs)

# ament_export_targets(export_${PROJECT_NAME} HAS_LIBRARY_TARGET)
# ament_export_dependencies(
#   rclcpp
# )

# install(
#   DIRECTORY include/
#   DESTINATION include
# )

# install(TARGETS
#   talker
#   EXPORT export_${PROJECT_NAME}
#   ARCHIVE DESTINATION lib
#   LIBRARY DESTINATION lib
#   RUNTIME DESTINATION bin
#   INCLUDES DESTINATION include
# )


ament_auto_package()
