cmake_minimum_required(VERSION 3.5.0)
project(ridgeback_hams_description)

if (ENV{ROS_VERSION} VERSION_EQUAL "1")

  find_package(catkin REQUIRED COMPONENTS)

  include_directories(
    ${catkin_INCLUDE_DIRS}
  )
  
  install(DIRECTORY meshes urdf
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
  )

  install(DIRECTORY scripts
    DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
  )

  catkin_package()

else()

  find_package(ament_cmake REQUIRED)

  install(DIRECTORY meshes urdf
    DESTINATION share/${PROJECT_NAME}
  )

  # TODO: figure out the ROS 2 equivalent for:
  # install(DIRECTORY scripts
  #   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
  # )

  ament_package()

endif()
