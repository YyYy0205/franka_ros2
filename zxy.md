# FRANKA R3

## 2.4 安装完成franka_ros2

官方example：
*【控制夹爪】roslaunch franka_gripper franka_gripper.launch robot_ip:=<fci-ip>

*【可视化】roslaunch franka_visualization franka_visualization.launch robot_ip:=<fci-ip> load_gripper:=<true|false>

*【运行Franka控制器】roslaunch franka_control franka_control.launch robot_ip:=<fci-ip> load_gripper:=<true|false> 

*【通过笛卡尔坐标运动】roslaunch franka_example_controllers cartesian_pose_example_controller.launch robot_ip:=<fci-ip> load_gripper:=<true|false> 
