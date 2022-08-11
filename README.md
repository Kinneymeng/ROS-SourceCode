### 使用说明

1.删除ROS工作空间下的所有文件，复制【src】文件夹到ROS工作空间，然后在工作空间运行命令“catkin_make”编译即可。

2.注意，移植到TX2主控的话，【kcf_track】功能包需要替换，TX2版的【kcf_track】功能包在与本文档在同一级目录下的文件夹【kcf_track\raspberry\kcf_track】。
扩展缓存命令：
sudo dd if=/dev/zero of=/swap bs=1M count=4096
sudo mkswap /swap
sudo chmod 600 /swap
sudo swapon -a /swap 
第一个命令执行需要8分钟
