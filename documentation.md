# Documentation

## Simulation

- imu: /imu_raw, sensor_msgs/Imu
  - 9-axis gyro, accelerometer, and magnetometer
- wheel encoders: /encoder/wheel_angles, sensor_msgs/JointState
  - angle of each wheel in radians
- camera images: /camera/rgb/image_raw, sensor_msgs/Image
- vehicle control: /cmd_vel, geometry_msgs/Twist
  - target linear/angular velocity (linear x is forward/reverse, angular z is rotation)
- gps: /gps/fix, sensor_msgs/NavSatFix

sensor noise parameters (when available) are specified in [mirv_description/urdf/mirv_gazebo.urdf.xacro](mirv_description/urdf/mirv_gazebo.urdf.xacro)

a few sensors are under [mirv_description/urdf](mirv_description/urdf)
a few models of things are under [mirv_description/meshes](mirv_description/meshes)

Had some issues with the GPS on 8/4/2022, solution was to add the lines: 
```
self.startingHeading = 0
self.startHeadSet = True
```
to the init method of globalToTruck.py
W