cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  ros-disthelper
  VERSION 0.1
  RELEASE beta
  SUMMARY "Distribution helpers for ROS."
  AUTHOR "Ralf Kaestner"
  CONTACT "ralf.kaestner@gmail.com"
  HOME "http://github.com/kralf/ros-disthelper"
  LICENSE "GNU Lesser General Public License (LGPL)"
  INSTALL /usr
  PREFIX ros-
)

remake_pack_deb(
  ARCH all
  DEPENDS ubash dpkg-dev devscripts
)

remake_distribute_deb(
  DISTRIBUTION lucid
  SECTION devel
  UPLOAD ppa:kralf/ros
  DEPENDS ubash dpkg-dev devscripts remake
  PASS CMAKE_BUILD_TYPE ROS_DISTHELPER_GIT_REVISION
)
remake_distribute_deb(
  DISTRIBUTION precise
  SECTION devel
  UPLOAD ppa:kralf/ros
  DEPENDS ubash dpkg-dev devscripts remake
  PASS CMAKE_BUILD_TYPE ROS_DISTHELPER_GIT_REVISION
)
remake_distribute_deb(
  DISTRIBUTION trusty
  SECTION devel
  UPLOAD ppa:kralf/ros
  DEPENDS ubash dpkg-dev devscripts remake
  PASS CMAKE_BUILD_TYPE ROS_DISTHELPER_GIT_REVISION
)
