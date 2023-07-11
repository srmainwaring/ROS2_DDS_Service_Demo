cmake_minimum_required(VERSION 3.16.3)

project("add_two_ints")

# Find requirements
find_package(fastcdr REQUIRED)
find_package(fastrtps REQUIRED)

find_package(microcdr REQUIRED)
find_package(microxrcedds_client REQUIRED)

add_executable(AddTwoInts
  AddTwoInts_main.cpp
  AddTwoInts_service.cpp
  AddTwoInts.cxx
  AddTwoIntsPubSubTypes.cxx
)
target_link_libraries(AddTwoInts
  fastcdr
  fastrtps
)

add_executable(AddTwoIntsMicro
  AddTwoInts_xrce.cpp
)
target_include_directories(AddTwoIntsMicro
  PRIVATE
  ${microcdr_INCLUDE_DIR}
  ${microxrcedds_client_INCLUDE_DIR}  
)
target_link_directories(AddTwoIntsMicro
  PRIVATE
  ${microcdr_LIB_DIR}
  ${microxrcedds_client_LIB_DIR}  
)
target_link_libraries(AddTwoIntsMicro
  microcdr
  microxrcedds_client
)
