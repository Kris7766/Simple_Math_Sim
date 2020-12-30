cmake_minimum_required(VERSION 3.0.2)
project(mini_project_2020)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED 
roscpp
geometry_msgs
)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if your package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES mini_project_2020
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
${catkin_INCLUDE_DIRS}
)

#Publishing_Math
add_executable(${PROJECT_NAME}_Publishing_Math src/Publishing_Math.cpp)
set_target_properties(${PROJECT_NAME}_Publishing_Math PROPERTIES OUTPUT_NAME Publishing_Math PREFIX "")
target_link_libraries(${PROJECT_NAME}_Publishing_Math
  ${catkin_LIBRARIES}
)

#Skildpadde_1
add_executable(${PROJECT_NAME}_Skildpadde_1 src/Skildpadde_1.cpp)
set_target_properties(${PROJECT_NAME}_Skildpadde_1 PROPERTIES OUTPUT_NAME Skildpadde_1 PREFIX "")
target_link_libraries(${PROJECT_NAME}_Skildpadde_1
  ${catkin_LIBRARIES}
)

#Skildpadde_2
add_executable(${PROJECT_NAME}_Skildpadde_2 src/Skildpadde_2.cpp)
set_target_properties(${PROJECT_NAME}_Skildpadde_2 PROPERTIES OUTPUT_NAME Skildpadde_2 PREFIX "")
target_link_libraries(${PROJECT_NAME}_Skildpadde_2
  ${catkin_LIBRARIES}
)


#############
## Install ##
#############

install(TARGETS 
${PROJECT_NAME}_Publishing_Math
${PROJECT_NAME}_Skildpadde_1
${PROJECT_NAME}_Skildpadde_2
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
