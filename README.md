# techman_tm5
A new driver for the TM5 robot arms from [Techman Robot.](http://tm-robot.com/) It is designed to provide another control method which is joint velocity control. By under joint velocity control, it could replace old version driver which only provide position control without speed changing and enhance more usability for lower-level control.
- This package is runing under Linux Ubuntu 14.04, not ROS supported.
- Some library packages(ex. tm_driver, tm_kinematics) were developed based on [kentsai0319/techman_robot](https://github.com/kentsai0319/techman_robot)
- The on-line trajectory generation algorithm ```/ReflexxesTypeII``` is from [Reflexxes Motion Library TypeII](http://www.reflexxes.ws/)
- ```/tm_reflexxes```package is developed based on APIs from ```/ReflexxesTypeII```

### Maintainer
[Howard Chen](https://github.com/s880367), <howardchen.ece04g@g2.nctu.edu.tw>, ISCI Lab, NCTU.


## Improvements
- ```/tm_driver``` :we add joint velocity control API inside. Also support for old version, position control.
**Note** : Please make sure your tm5 is supported for joint velocity command.
- ```tm_kinematics``` : forward/inverse jacobian generation supported.
- ```tm_reflexxes``` : On-line trajectory generation under joint velocity supported.
- All the packages are ROS supported ready.

## Update
The libraries inside the package are still keep updating and being developing for newer functions and improving better usability. For the lastest version of packages, please check out the following individual files : 
- tm_driver : [ISCI-NCTU/tm_reflexxes/tm_driver](https://github.com/ISCI-NCTU/tm_reflexxes)
- tm_kinematics : [s880367/tm_jacobian/tm_kinematics](https://github.com/s880367/tm_jacobian)
- tm_reflexxes : [ISCI-NCTU/tm_reflexxes/tm_reflexxes](https://github.com/ISCI-NCTU/tm_reflexxes)

## Installation
- For building the package requre [Eigen3](http://eigen.tuxfamily.org/index.php?title=Main_Page)
```
mkdir build && cd build
cmake ..
make
```
## Usage
- ```/tm_bringup``` is used form bring up the real physical robot
```
./tm_bringup [robot_ip] (default robot_ip is 192.168.0.10)
```
- ```/tm_otg``` is a trajectory simulation program that could used to simulate trajectory by printint out joint position and velocity at each time stamp. (The frequency in the library is set to 25ms.)

