# FRANKA R3
### 环境要求
<img width="710" height="220" alt="截屏2026-02-05 12 25 15" src="https://github.com/user-attachments/assets/7ed522bd-5a49-42b5-921e-7be803456e26" />
<img width="626" height="106" alt="截屏2026-02-04 19 30 10" src="https://github.com/user-attachments/assets/65f5a47f-b76c-40eb-9736-e4c10e26d346" />

## 环境配置
    > Ubuntu 22.04
    > ROS 2 humble
    > Robot System Version:  要求>= 5.7.2 -- 满足 5.8.1
    > Robot serve 9 
    > libfranka Version 要求0.18.0>= 0.15.0 -- 满足 0.17.0
    > franka_ros2 (Humble) 要求 v2.0.2 < v3.0.0 满足 2.2.1
* Desk帐号：franka / franka_so
* 密码：franka123  / frankaso123
* workspace：franka_ros2_ws
## Franka 配置
* 先通过网线连接机械臂，在网址输入：`robot.franka.de`进入Desk 
    > 在setting中设置静态IP：172.16.0.2 掩码：255.255.252.0
    >> 把PC也设置为静态IP，在相同网段都可访问机械臂

  
## 2.4 
 1. Pico 打通
 2. Local Machine Installation 
  按照README安装，可能出现rosdep错误
 > rosdep install --from-paths src --ignore-src --rosdistro humble -y
 3. 成功安装franka_ros2
 4. Test the build 
> `colone test`成功
> >命令：` ros2 launch franka_fr3_moveit_config moveit.launch.py robot_ip:=dont-care use_fake_hardware:=true`
 4. ERROR: server 版本9，电脑libfranka版本10
> 问题：libfranka Version 要求0.18.0>= 0.15.0 现在0.19.0不满足
> >解决：降级libfranka 库到0.17.0

## 2.5
 1. 运行示教模式
> 容易出现force throshold错误
>>扩大force throshold的值，并换一个更稳的桌子
 2. 运行`ros2 launch franka_bringup franka.launch.py robot_type:=fr3 robot_ip:=<fci-ip> use_rviz:=true`
> 无报错，但不显示rviz
>>
3. 创建安全员，并配置watchman
> 可设置机械臂安全工作空间
4. 通过franka_ros2 控制夹爪
> `ros2 launch franka_bringup example.launch.py controller_names:=gripper_example_controller gripper=true`

## 2.6
 1. 编辑机械臂双相机的配置文件
> left_right_sensor_suite.yaml

