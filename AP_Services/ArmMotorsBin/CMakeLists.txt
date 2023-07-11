
cmake_minimum_required(VERSION 3.16.3)

project("arm_motors_bin")

# Find requirements
find_package(microcdr REQUIRED)
find_package(microxrcedds_client REQUIRED)

add_executable(ArmMotorsBinMicro
  ArmMotorsBin_xrce.cpp
)
target_include_directories(ArmMotorsBinMicro
  PRIVATE
  ${microcdr_INCLUDE_DIR}
  ${microxrcedds_client_INCLUDE_DIR}  
)
target_link_directories(ArmMotorsBinMicro
  PRIVATE
  ${microcdr_LIB_DIR}
  ${microxrcedds_client_LIB_DIR}  
)
target_link_libraries(ArmMotorsBinMicro
  microcdr
  microxrcedds_client
)

