
cmake_minimum_required(VERSION 3.16.3)

project("ap_services_bin")

# Find requirements
find_package(microcdr REQUIRED)
find_package(microxrcedds_client REQUIRED)

add_executable(ArmMotorsBinMicro
  Arm_Motors_DDS_Server_Bin.cpp
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

