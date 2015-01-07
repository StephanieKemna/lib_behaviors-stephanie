#*****************************************************************#
#*    Name: Stephanie Kemna,                                     *#
#*    Orgn: University of Southern California, LA, CA            *#
#*    File: CMakeLists.txt                                       *#
#*    Date: Dec 12, 2014                                         *#
#*****************************************************************#

#-------------------------------------------------------------
# The CMakeLists.txt for:                     BHV_WaypointSpd
#-------------------------------------------------------------

SET(CMAKE_VERBOSE_MAKEFILE ON)

GET_FILENAME_COMPONENT(KEMNA_SRC_DIR_ABS .. ABSOLUTE)

FILE(GLOB IVP_INCLUDE_DIRS 
   ${IVP_SRC_DIR_ABSOLUTE}/lib_behaviors
   ${IVP_SRC_DIR_ABSOLUTE}/lib_ivpbuild
   ${IVP_SRC_DIR_ABSOLUTE}/lib_logic
   ${IVP_SRC_DIR_ABSOLUTE}/lib_ivpcore 
   ${IVP_SRC_DIR_ABSOLUTE}/lib_bhvutil
   ${IVP_SRC_DIR_ABSOLUTE}/lib_mbutil
   ${IVP_SRC_DIR_ABSOLUTE}/lib_geometry
   )

INCLUDE_DIRECTORIES(${IVP_INCLUDE_DIRS})

#-------------------------------------------------------------
#                                             BHV_WaypointSpd
#-------------------------------------------------------------
ADD_LIBRARY(BHV_WaypointSpd SHARED BHV_WaypointSpd.cpp)
TARGET_LINK_LIBRARIES(BHV_WaypointSpd
  behaviors ivpbuild logic ivpcore bhvutil mbutil geometry)

#-------------------------------------------------------------
