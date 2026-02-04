# FRANKA R3

## 2.4 
### 环境
    > Ubuntu 22.04
    > ROS 2 humble
    > Robot System Version:  要求>= 5.7.2 -- 满足 5.8.1
    > Robot serve 9 
    > libfranka Version 要求0.18.0>= 0.15.0 不满足 0.19.0
    > franka_ros2 (Humble) 要求 v2.0.2 < v3.0.0 满足 2.2.1
    
 1. Local Machine Installation 
  按照README安装，可能出现rosdep错误
 > rosdep install --from-paths src --ignore-src --rosdistro humble -y
 2. 成功安装franka_ros2
 3. Test the build 
> `colone test`成功
> >` ros2 launch franka_fr3_moveit_config moveit.launch.py robot_ip:=dont-care use_fake_hardware:=true`
 4. ERROR: server 版本9，电脑版本10
> >问题：libfranka Version 要求0.18.0>= 0.15.0 现在0.19.0不满足 
  


官方example：
* 控制夹爪 `roslaunch franka_gripper franka_gripper.launch robot_ip:=<fci-ip>`
* 可视化 `roslaunch franka_visualization franka_visualization.launch robot_ip:=<fci-ip> load_gripper:=<true|false>`
* 运行Franka控制器 `roslaunch franka_control franka_control.launch robot_ip:=<fci-ip> load_gripper:=<true|false> `
* 通过笛卡尔坐标运动 `roslaunch franka_example_controllers cartesian_pose_example_controller.launch robot_ip:=<fci-ip> load_gripper:=<true|false> `
