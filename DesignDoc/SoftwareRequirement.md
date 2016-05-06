## 项目需求

机械学院大楼共七层，大楼南入口有两部电梯同时工作，请为南入口开发基于PLC的电梯控制系统。

### 控制系统硬件

- 每层电梯口有两个按钮“上行”和“下行”，有两个LED数码管分别显示左右两个电梯所在的楼层，数码管旁有箭头LED灯指示该电梯的运行状态（向上，向下，停止）。如下图所示：

![](http://images2015.cnblogs.com/blog/810896/201604/810896-20160419231454585-513190023.jpg)


- 电梯轿厢内有从“1”到“7”共7个数字按钮用来选择目的楼层，每个按钮上有个LED灯指示该层被选中。有一个LED数码管显示当前楼层，有“开”和“关”两个按钮用来手动开关电梯门，如下图所示：

![](http://images2015.cnblogs.com/blog/810896/201604/810896-20160419231513241-1733266456.jpg)


- 每部电梯由一台交流异步变频电机和变频器控制，PLC给变频器发送三个开关量信号：正转、反转、停止。
- 电梯每层有一个平层行程开关用于检测电梯轿厢是否到达该层，电机的加减速时间忽略不计，当PLC检测到某一层的行程开关后立即给变频器发出停止信号，可认为能够保证电梯准确停在该层。
- 电梯轿厢内安装有开门到位和关门到位两个行程开关。

###电梯功能需求

- 当有人按下楼层的上行和下行按钮时，电梯控制系统调度一部电梯尽快到达乘客所在的楼层，
- 电梯轿厢在楼层停稳后延迟2秒钟打开电梯门，电梯门打开后延迟10秒后电梯门自动关闭，在此期间如有人按下关闭按钮则立即关闭电梯门。在电梯门关闭过程中如有人在外面按下与电梯运行方向一致的按钮或有人在轿厢内按下开门按钮，则电梯门再次打开，一旦电梯门关闭，则不再响应按钮。
- 两部电梯的调度策略可由开发者灵活定义，以整体上节约乘客等待时间和节约能耗为评价标准。

## 设计要求

### 第一阶段 （Deadline 4月29日）

每位同学提交概要设计文档，内容包括：
1. 系统硬件接口定义
2. 系统功能定义
3. 软件功能模块分解和模块间接口定义

### 第二阶段 

全班同学分为4组，每组6-7人，选出组长1名，根据之前的概要设计文档讨论形成小组的概要设计文档用于指导详细设计。
组长负责任务分解，在Automation Studio上开发电梯控制软件，教师负责提供软件项目模板，内部含有电梯模型和电梯运行仿真图形界面。
开发工作基于Github进行，每位成员通过Github提交自己的开发文档。

### 第三阶段 

项目组进行总结，撰写结题文档，进行项目验收评比，通过模拟多名乘客随机乘坐电梯的场景，评比各个小组的控制系统性能指标。评选优秀小组和优秀组员。