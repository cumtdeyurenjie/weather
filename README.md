# 采集数据说明文档
#  Dataset Documentation
数据包括激光雷达点云数据，惯导系统数据以及点云时间戳数据。

The Dataset provides LIDAR point cloud, Inertial Navigation System Data and point cloud timestamp.
## 传感器摆放方式
##  Sensor Placement
雷达在惯导上方150cm 
雷达在惯导左面18cm
雷达在惯导前面73cm

The LIDAR is 150cm above the INS.
The LIDAR is 18cm to the left of the INS.
The LIDAR is 73cm in front of the INS.
### 1. 激光雷达点云数据
### 1. LIDAR point cloud data
**未去畸变**的激光雷达数据以点云PCD文件形式存储，存放于/lidar1 文件夹下。
PCD 点云文件中的点包括XYZIRT 信息。其中xyz是单精度浮点数 ，intensity也是单精度浮点数，ring是16位两字节无符号整数，time是8字节双精度浮点数，也就是一个double。

**The undistorted LIDAR point cloud** is stored in the form of PCD files in the /lidar1 folder.

Points in a PCD point cloud file include XYZIRT information. Among them, xyz is a single-precision floating-point number, intensity is also a single-precision floating-point number, ring is a 16-bit two-byte unsigned integer, and time is an 8-byte double-precision floating-point double type.
### 2. 惯性导航系统数据
### 2.Inertial Navigation System Data
存放于/npos220s.txt 文件中。其中IMU 数据带有Imu 前缀。里程计数据带有Odometry 前缀。

The data is stored in the /npos220s.txt file. The IMU data is prefixed with Imu. The Odometry data is prefixed with Odometry.
#### 2.1 IMU 信息

 1. 浮点型时间戳
 2. XYZ 
 3. Roll Yaw Pitch
#### 2.1 IMU data
 1. Timestamp
 2. XYZ
 3. Roll Yaw Pitch
#### 2.2 里程计信息
存储了相对于起始位置的位姿变化信息
 1. 时间戳
 2. XYZ
 3. 四元数
 4. XYZ和ground_truth 的标准差

#### 2.2 Odometry data
Stores the pose change information relative to the starting position.

1. Timestamp
2. XYZ
3. Quaternion
4. Standard deviation of XYZ and ground_truth

### 3. 点云时间戳数据
存放于/lidar1_timestamp.txt 文件中。存储了每一帧点云的采集时间。
### 3. Point Cloud Timestamp Data
Stored in the /lidar1_timestamp.txt file. The acquisition time of each frame point cloud is stored.
