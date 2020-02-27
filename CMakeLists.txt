cmake_minimum_required(VERSION 3.5.0)
project(ridgeback_hams_description)

if ($ENV{ROS_VERSION} VERSION_EQUAL "1")

  find_package(catkin REQUIRED COMPONENTS)

  include_directories(
    ${catkin_INCLUDE_DIRS}
  )
  
  catkin_package()

else()

  find_package(ament_cmake REQUIRED)

  ament_package()

endif()

install(DIRECTORY 
  meshes
  urdf
  DESTINATION share/${PROJECT_NAME}/
)

