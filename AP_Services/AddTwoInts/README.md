# AddTwoInts

## Usage (FastDDS)

Micro XRCE Agent:

```bash
cd ~/ws
$ MicroXRCEAgent udp4 -p 2019 -v6
```

Micro XRCE Client:

```bash
cd ~/ws/src/ROS2_DDS_Service_Demo/AP_Services/AddTwoInts/build
$ ./AddTwoIntsMicro 127.0.0.1 2019
```

FastDDS Client:

```bash
cd ~/ws/src/ROS2_DDS_Service_Demo/AP_Services/AddTwoInts/build
./AddTwoInts -m client -c 1
```

## Usage (ROS 2)

Integration Service:

```bash
LD_LIBRARY_PATH=$(pwd)/install/is-fastdds/lib integration-service $(pwd)/src/ROS2_DDS_Service_Demo/AP_Services/AddTwoInts/AddTwoInts_fastdds.yaml --is-prefix-path $(pwd)/install/is-ros2/lib/is/ros2 --is-prefix-path $(pwd)/install/is-ros2-mix-generator/lib/is
```

ROS 2 CLI:

```bash
ros2 service call /add_two_ints example_interfaces/srv/AddTwoInts "{a: 5, b: 17}"
```
