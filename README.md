### 一、使用说明

1.删除ROS工作空间下的所有文件，复制【src】文件夹到ROS工作空间，然后在工作空间运行命令“catkin_make”编译即可。

2.注意，移植到树莓派主控的话，【kcf_track】功能包需要替换，树莓派版的【kcf_track】功能包在与本文档在同一级目录下的文件夹【kcf_track\raspberry\kcf_track】。
同时2GB内存的【树莓派4B】，需要进行缓存扩展后才可以进行编译，否则会树莓派会卡死。扩展缓存命令：
sudo dd if=/dev/zero of=/swap bs=1M count=4096
sudo mkswap /swap
sudo chmod 600 /swap
sudo swapon -a /swap 
第一个命令执行需要8分钟

3.如果只是适配不同车型，只需要按照以下二、三、四说明修改参数即可

### 二、功能包【turn_on_wheeltec_robot】

1.文件【turn_on_wheeltec_robot\launch\turn_on_wheeltec_robot.launch】
根据实际小车修改车型

2.文件【turn_on_wheeltec_robot\launch\rrt_slam.launch】
根据实际小车修改车型

3.文件【turn_on_wheeltec_robot\launch\include\teb_local_planner.launch】
根据实际小车修改车型

4.文件【turn_on_wheeltec_robot\launch\include\teb_local_planner_pure3d.launch】
根据实际小车修改车型

5.文件【turn_on_wheeltec_robot\launch\include\dwa_local_planner.launch】
根据实际小车修改车型

6.文件【turn_on_wheeltec_robot\launch\include\dwa_local_planner_pure3d.launch】
根据实际小车修改车型

7.文件【turn_on_wheeltec_robot\launch\navigation.launch】
修改局部路径规划器算法，一般差速小车选择dwa算法、非差速小车选择teb算法

8.文件【turn_on_wheeltec_robot\launch\include\rtabmap_nav.launch】
修改局部路径规划器算法，一般差速小车选择dwa算法、非差速小车选择teb算法

9.文件【turn_on_wheeltec_robot\launch\pure3d_navigation.launch】
修改局部路径规划器算法，一般差速小车选择dwa算法、非差速小车选择teb算法

10.文件【turn_on_wheeltec_robot\param_common\teb_local_planner_params.yaml】
根据车型修改参数，文件内有对应注释

11.文件【turn_on_wheeltec_robot\scripts\cmd_vel_to_ackermann_drive.py】
阿克曼小车才需要修改的文件，参数“wheelbase”,文件内有对应注释