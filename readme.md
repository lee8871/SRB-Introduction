# 简单机器人总线（Simple Robotic Bus，SRB）
`李阳` `lee8871@126.com`

## 什么是简单机器人总线
简单机器人总线，简单的说，机器人包含大量的控制器和传感器，将传感器和控制器连的数据送给控制算法是个令人头疼的问题。SRB是一条总线，将这些设备都连在上面。通过SRB的协议，机器人的控制算法就可以获取传感器的数据以及发送指令给控制器。</br>
## SRB通信
SRB是主从式的总线网络。SRB主机决定了什么时候进行总线访问。访问指的是主机向某个节点发送命令（例如电机预期的转速），然后节点发给主机传感器采集到的数据。</br>
通常情况下，主机访问所有节点，得到各个传感器的数据，然后运算出下一周期发给节点的命令，再进行下一次访问，如此循环。
## SRB主机
很多设备都可以成为SRB主机。使用微控制器的UART接口连接**UART转SRB模块**，就可以作为SRB主机。我们推荐使用Arduino Leonardo作为SRB主机，[并提供Arduino驱动库](https://github.com/lee8871/SRB-master-arduino)
此外,使用**USB转SRB模块**（使用libusb驱动），可以让任何USB设备成为SRB主机。包括：
* 电脑win10系统 [并提供dotNet-SRB-master-Frame](https://github.com/lee8871/SRB-Frame-dotNet)
* linux系统 C++库和Python库正在开发
* ROS(ROS是Linux下的软件) C++库和Python库正在开发
* 树莓派 库正在开发
* 友善之臂 库正在开发
