# 作品集-杨康韦

邮箱: [1720077273@qq.com](mailto:1720077273@qq.com)

## 硬件作品

### 全国机器⼈⼤赛RoboMaster2024 主动均衡电容组 2023.09-2024.01

* 将⼴城理开源的主动均衡电容组进⾏⼩型化，迭代3次后成功将PCB尺⼨优化⾄58*75mm 以下是为飞镖电源系统设计的**主动均衡电容组功能说明**，针对多电容串联场景的电压平衡与寿命优化方案：


### **主动均衡电容组功能设计**

#### **核心目标**

解决串联电容组因个体差异导致的**电压失衡问题**，防止单电容过充/过放，提升整体能量利用率与循环寿命。


### **技术实现方案**

纯硬件实现，通过4个MOS管的拓扑来将每个电容分别在每个周期的一半去并联、另一半来串联，并联时可以平衡不同电容之间的电压，串联时可以进行所有电容的充电与放电

#### **关键性能参数**

* **效率**：＞87%（2A均衡电流下）
* **工作温度**：-20℃~65℃（满足赛场环境）
* **均衡频率**：20kHz

### **应用收益**

#### **修复原设计痛点**

* **循环寿命提升3倍**
通过主动均衡防止单电容过压（>3.7V），规避电极损伤
* **有效容量增加15%**
均衡后电容组放电截止电压一致性提高
* **降低80%维护成本**
避免因电压失衡导致的个别电容报废而需要拆开机器人修理的麻烦

### **工程适配要点**

1. **空间占用**
  * 整体模块尺寸仅为58*75mm
2. **热管理**
  * 线性稳压芯片需要加装小型散热片

![主动均衡电容原理图](https://github.com/KangweiYang/personal-portfolio/blob/main/AWCapGroup_sche.png?raw=true)

![主动均衡电容PCB图](https://github.com/KangweiYang/personal-portfolio/blob/main/AWCapGroup_pcb.png?raw=true)

![主动均衡电容3D渲染图](https://github.com/KangweiYang/personal-portfolio/blob/main/AWCapGroup_3d.png?raw=true)


---
### 无控飞镖电源板 2024.10-2024.11

### **核心功能**

1. **磁控启停系统**
  * **双极性自锁霍尔开关（型号U18）**
    * 使用磁铁靠近即触发：N极开电/S极关电，动作后移开磁铁仍保持状态
    * **注意**：剧烈撞击可能导致意外重启（非致命缺陷）
2. **高效供电架构**
  * **锂离子电容供电（2.5~4V）**
    * 容量400mAh（支持镖头亮灯约20分钟）
    * **保护机制**：过放保护（<2.7V自动断电），禁止放电至2.5V以下！
  * **5V升压输出**
    * 为飞镖系统提供稳定主电源
3. **双冗余Type-C充电**
  * 配置2个立插14P鱼叉母座（垂直焊接增强强度）
  * 兼容5V/1A输入（支持Type-C充电头/USB-A充电宝）
4. **全面电源保护**
  * **三重防护机制**：
    * 低压关断（过放保护）
    * 输入浪涌抑制
    * 输出过压/过流保护（覆盖5V & 3.3V线路）

---

* 开源链接(含介绍):https://bbs.robomaster.com/article/714435
  * (工程文件)https://oshwhub.com/flxi/scurm2025-hotpot-dart-power
* 演示视频：https://www.bilibili.com/video/BV1Qg5qz3Evf/

  
![无控飞镖电源板PCB图](https://github.com/KangweiYang/personal-portfolio/blob/main/HALL_sche.png?raw=true)

![无控飞镖电源板PCB图](https://github.com/KangweiYang/personal-portfolio/blob/main/HALL_board.png?raw=true)

![无控飞镖电源板3D渲染图](https://github.com/KangweiYang/personal-portfolio/blob/main/HALL_3d.png?raw=true)

---
### 飞镖架STM32拓展板 2024.09-至今

* 功能:
  * 输入电源缓启动(24V)
  * 光耦信号隔离(24V信号)
  * RS485收发
  * CAN收发
  * MOS管做24V继电器，后级再接缓启动
  * 电源保护(5V & 3.3V)
    1. 低压关断
    2. 过压保护
    3. 过流保护
    4. 浪涌抑制

![飞镖架STM32拓展板PCB图](https://github.com/KangweiYang/personal-portfolio/blob/main/MAINcontrol_PCB.png?raw=true)

![飞镖架STM32拓展板3D渲染图](https://github.com/KangweiYang/personal-portfolio/blob/main/MAINcontrol_3D.png?raw=true)
