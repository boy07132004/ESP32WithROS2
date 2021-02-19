# SensorWithROS2

### Devices

* Raspberry Pi (Ubuntu 20.04)
* ESP32

### Version

|ros2arduino|ROS2|MicroXRCEAgent|
|:---------:|:---------:|:---------:|
|0.2.1|dashing|v1.3.0 |

### ROS2

I use a docker container to build ROS2 environment.

```Bash
$ docker run -it --net=host -v /dev:/dev --privileged --name container_name ros:dashing
```

* In  container
```Bash
$ apt update && rosdep update
$ git clone -b v1.3.0 https://github.com/eProsima/Micro-XRCE-DDS-Agent.git
$ cd Micro-XRCE-DDS-Agent
$ mkdir build && cd build
$ cmake ..
$ make
$ make install
$ sudo ldconfig /usr/local/lib/

$ MicroXRCEAgent udp -p 8888     # set the port you want
```

