# 简单机器人总线（Simple Robotic Bus，SRB）
`李阳` `lee8871@126.com`

## 什么是简单机器人总线
简单机器人总线，简单的说，机器人包含大量的控制器和传感器，组织这些传感器和控制器是个令人头疼的问题。</br>
SRB是一条总线，可以将这些设备都连入其中。SRB主机可以是**ROS**、**树莓派**、**dotNet桌面应用** 或者 **Arduino**。它们可以简单、快速地访问机器人的控制器和传感器。

## SRB的优势
* 添加节点非常简单，接线容易，不需修改驱动，设计者可以飞快的迭代机器人设计。
* PC到机器人设备的实时通信，实时周期可以达到1kHz。
* SRB遵守实现一种功能有且最好仅有一种方法的设计理念，例程丰富，文档完善。

## SRB接线方法





## SRB主机
很多设备都可以成为SRB主机。使用微控制器的UART接口连接**UART转SRB模块**，就可以作为SRB主机。
* 各种MCU 使用**UART转SRB模块**。
* Arduino Leonardo作为SRB主机，[并提供Arduino驱动库](https://github.com/lee8871/SRB-master-arduino)

此外，使用**USB转SRB模块**（使用libusb驱动），可以让任何USB设备成为SRB主机。包括：
* 电脑win10系统 [并提供dotNet-SRB-master-Frame](https://github.com/lee8871/SRB-Frame-dotNet)
* linux系统 C++库和Python库正在开发
* ROS(ROS是Linux下的软件) C++库和Python库正在开发
* 树莓派 C++库和Python库正在开发
* 友善之臂 C++库和Python库正在开发
*
## SRB节点
**SRB总线接入设备**
1.  SRB转ARDUINO</br>
1.  SRB转USB（就像SRB连接Ardouino一样，SRB转USB提供电脑或者树莓派等设备对SRB的直接控制。区别于现有设备，USB可以提供更极限快速的访问速度，也是SRB进入ROS系统的门户。）

**目前已有的节点：**
1.  SRB双电机控制器

**即将完成的节点：**
1.  SRB姿态传感器（用于识别机器人自身位置）</br>
1.  SRB带有测速的电机驱动（可以获得精确的速度控制，作为里程计可以推测机器人的运行轨迹和当前位置）</br>
1.  SRB电池管理器（可以监测电池的电量，可以完成充电）</br>

**预计有这些节点：**
1.  SRB红外传感器（用于寻迹黑线，机械臂碰撞检测）</br>
1.  SRB带有力传感器的电机驱动（测量机械手的握力大小）</br>
1.  SRB超声测距节点</br>
2.  电阻/电压传感器节点</br>
