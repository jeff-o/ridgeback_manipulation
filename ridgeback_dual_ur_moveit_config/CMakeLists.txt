cmake_minimum_required(VERSION 2.8.3)
project(ridgeback_dual_ur_moveit_config)

find_package(catkin REQUIRED)

catkin_package()

install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
install(DIRECTORY config
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
install(DIRECTORY scripts
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)
  roslaunch_add_file_check(launch/move_group.launch)
  roslaunch_add_file_check(launch/ridgeback_dual_ur_moveit_planning_execution.launch)
endif()
