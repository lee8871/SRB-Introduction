# 自序
`李阳` `lee8871@126.com`</br></br>
这篇文章讲述了我们为什么要开发SRB总线，以及SRB将解决哪些问题。这只是我们团队的想法，我们并不强求您认可我们的想法。</br>
## 机器人驱动程序设计的困扰
随着3D打印和CAD技术日渐成熟，机器人的设计变得越来越简单。除了机械部分，想让机器人动起来，还需要电机和控制器，想要自动完成某些工作，还需要传感器。
机械工程师往往不擅长电子线路的设计。他们使用Arduino来实现自己的想法。</br>
当传感器的数量多起来的时候，事情就变了，比如需要3个电机的时候，端口就可能不够用，如果同时需要超声测距，超声和电机可能用到同一个定时器。</br>
事实上，任何使用MCU的机器人设计都会遇到这样的问题。一个优秀的嵌入式工程师会在设计前就确定电机和传感器的数量，然后选择合适的MCU。如果算法工程师要求额外添加传感器或者控制器，嵌入式工程师一定会抓狂，因为添加传感器可能导致MCU的资源不够用，必须选择新的MCU，这意味着全部重新设计。</br>
另一方面，将采集到的数据传给电脑一直是个不太好解决的问题，除非用专门的PCI板卡。数据传输大多选择串口，而串口的通讯速度并不高，这一点让系统的实时性变得很低。</br>

## 服务机器人发展
简单的说，人工智能 + ROS 必然会融合在服务机器人这一领域，这不仅是预言，也是早已开始发生的事情。</br>
服务机器人工作在非结构化环境，必然需要传感器来采集环境的信息。现有的机器人传感器研究局限在激光雷达和摄像头，而触觉传感器，超声测距这样的小型传感器却很少见到大量安装。有些机器人只有手指尖装有压力传感器，而机械臂碰到东西时，机器人却浑然不知。</br>
像生物一样，机器人不仅需要几个个大型传感器，还需要大量的小型传感器。比如“皮肤”上布满检测物体接近的光电传感器，每个可动部分上安装陀螺仪，以及辅助视觉的超声测距器，辅助触觉的电阻传感器。神经网络也非常希望融合这些数据完成更好的控制。</br>
显然不可能将这些传感器都接到核心控制器上进行数据采集，上百条导线绝对会让维护和安装人员直接崩溃。怎么将这些传感器数据传回机器人的“大脑”，就是一个需要解决的问题。</br>

## SRB主要特点
SRB是一条专为机器人设计的总线。
* SRB选择了最方便的IDC接插件，让传感器的接入非常简单。
* 使用SRB设备完全不需要驱动编程。
* SRB基于485总线，波特率为2Mb/s，实际控制时，控制周期可以达到1kHz~100Hz，具体依节点的数量而定。
* 使用SRB可以通过LibUSB接入USB主机。设备包括dotNet Windows程序，Linux系统，树莓派，支持C++和python（正在开发），可以接入ROS（正在开发）。
* 支持使用Arduino。
* 支持使用Windows可视窗体程序进行总线管理和节点配置。




　　
