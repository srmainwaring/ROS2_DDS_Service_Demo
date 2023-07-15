# AP_Services

## Prerequisites
- Install [ROS-2 Humble](https://docs.ros.org/en/humble/Installation.html)
- Install the necessary ROS-2 packages in [ardupilot_ros2](https://github.com/arshPratap/ardupilot_ros2) 
    - switch to the **ArmingClient** branch
    - build the [ap_custom_services](https://github.com/arshPratap/ardupilot_ros2/tree/ArmingClient/ap_custom_services) package
    - build the [ap_service_clients](https://github.com/arshPratap/ardupilot_ros2/tree/ArmingClient/ap_service_clients) package
- Install [Micro-XRCE-Agent](https://micro-xrce-dds.docs.eprosima.com/en/latest/installation.html#installing-the-agent-standalone)
- Install [Micro-XRCE-Client library](https://micro-xrce-dds.docs.eprosima.com/en/latest/installation.html#installing-the-client-standalone)
- Install [Integration Services](https://integration-service.docs.eprosima.com/en/latest/installation_manual/installation.html) : 
    - Get system handles for [Fast-DDS](https://github.com/eProsima/FastDDS-SH)
    - Get system handles for [ROS 2](https://github.com/eProsima/ROS2-SH)
    - Install the integration service by running the following command :

      ```bash
      colcon build --cmake-args -DCMAKE_BUILD_TYPE=RelWithDebInfo -DUAGENT_LOGGER_PROFILE=ON -DUAGENT_USE_SYSTEM_LOGGER=OFF -DMIX_ROS_PACKAGES="example_interfaces ap_custom_services"
      ```

## Examples

- AddTwoInts
- ArmMotors
- ArmMotorsBin
- ArmMotorsInt64
