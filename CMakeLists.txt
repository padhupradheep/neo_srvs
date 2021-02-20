cmake_minimum_required(VERSION 3.5)
project(neo_srvs)

## By default build with code optimization and no debug info
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(rosidl_generate_interfaces
  "srv/RelayBoardSetRelay.srv"
  "srv/IOBoardSetDigOut.srv"
  "srv/RelayBoardSetLCDMsg.srv"
  "srv/LockPlatform.srv"
  "srv/UnlockPlatform.srv"
  "srv/ResetOmniWheels.srv"
  "srv/RelayBoardSetEMStop.srv"
  "srv/RelayBoardUnSetEMStop.srv"
)


ament_package()
