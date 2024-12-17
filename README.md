# TurtleBot4_simulator
Avaliable workspace

1.解压压缩文件
cd ~

mkdir test_ws

cd test_ws
tar --strip-components=1 -xzvf ~/dev_ws.tar.gz

2.删除已存在的编译文件
cd ~/test_ws
rm -rf build install log

3.重新构建工作空间(colcon build 重新编译)
cd ~/test_ws
colcon build --symlink-install

4.测试环境变量配置
source ~/test_ws/install/setup.bash


5.启动仿真与测试
ros2 launch turtlebot4_ignition_bringup turtlebot4_ignition.launch.py slam:=true nav2:=true rviz:=true

Simulate with map
ros2 launch turtlebot4_ignition_bringup turtlebot4_ignition.launch.py nav2:=true slam:=false localization:=true \
rviz:=true world:=warehouse map:=/home/myra/test_ws/dev_ws/src/turtlebot4/turtlebot4_navigation/maps/warehouse.yaml
(map location)
