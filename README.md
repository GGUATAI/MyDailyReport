# MyDailyReport
GUATAI的日报仓库

5.13
日报第一天：改进以前写的PID,引入微分先行，不完全微分，抗积分饱和，变积分等；改良校内赛车车的遥控时序

5.14
日报第二天：测试校内赛车车的所有舵机，再改良校内赛车车的遥控时序； 查阅DT7遥控器的手册

5.15
日报第三天：处理一堆破事，啥事没干×_×

5.16
日报第四天：学习MATLAB的使用（初步），感觉发烧了今天又是啥事没干

5.17
日报第五天：初步了解电赛，了解题型和规则；学习MATLAB的使用（二维，三维图形的绘制，矩阵构造），确实发烧了今天再是啥事没干

5.18
日报第六天：看C板的开源，编写DT7遥控的程序

5.19
日报第七天：继续看大疆C板的开源，对于昨天编写的DT7遥控程序里具体的数据接收与处理进行深一步了解，例如DMA和串口的程序编写与我以前写的有点不同

5.20
日报第八天：编写底盘电机代码，参考了大疆C板开源，结合队内代码规范修改，并比较以前写的电机驱动代码，调整代码具体写法

5.21
日报第九天：检查校内赛车车的问题

5.22
日报第十天：继续完善任务的底盘电机代码

5.23
日报第十一天：检查校内赛车车的舵机问题+修改之前写的CAN通信代码

5.24
日报第十二天：借用DT7遥控器，查看是否能接收正常数据，修改代码

5.25
日报第十三天：校内赛＋补作业

5.26
日报第十四天：补作业，DDL了

5.27
日报第十五天：查阅一下全向轮移动的网络资料

5.28
日报第十六天：学习四全向轮移动的原理以及具体的代码实现（待编写）

5.29
日报第十九天：今天发现虽然遥控器和底盘电机代码已经编写完成，但对于完成任务的要求以及后续对于此代码的增加，遥控器和底盘电机代码还不足以支持需求，所以今天给遥控器的相关代码加了错误判断和断连判断用来防止遥控数据出错导致的连锁反应，以及去重新学习一下freertos的任务通知功能。

5.30
日报第二十天：今天编写遥控器控制底盘四个电机前后左右移动的代码，因为刚开始写的时候还加上了云台以及底盘6020的代码，想整个跟随角度移动，显得有点繁杂很难看，而且也不太会写，所以删掉了这个6020部分，同时修改之前遥控器代码部分，删去一些暂时用不到的功能，让代码简洁一些也方便后边调试，基本的功能可以说已经完成，但是细节还得改，具体能不能动还得烧录看看效果，还有就是发现unknown type name错误有可能是因为头文件在另一文件头部分，循环引用导致，就是两个.h文件里互相import

5.31
日报第二十一天：今天烧录测试代码，遥控能够移动底盘，但奇怪的是四号轮不动，然后现在因为PID用的是普通的PID,所以之后打算把之前写的位置式PID且带有不完全微分，抗积分饱和，变积分，死去等等，加到现在的代码再看看效果，现在底盘走得歪歪扭扭的。还有就是今天发现把底盘代码加进去后串口接收和发送变异常了，结果是一个函数需要传空指针，我没有传导致的，真神奇

6.1
日报第二十二天：电脑拿去修了，今天写作业

6.2
日报第二十三天：做作业数电综合设计

6.3
日报第二十四天：给底盘程序换上自己的pid并调整底盘任务代码结构（还没做完）

6.4
日报第二十五天：今天没有干相关的事

6.5
日报第二十六天：底盘程序暂时换好了自己的pid，但还有一些没换上去，感觉现在还不需要

6.6
日报第二十七天：烧录新的代码给底盘，调整了底盘任务代码和底盘状态代码的结构和具体编写，使其更符合规范和方便自己在日后的改写

6.7到6.10
日报第二十八天到三十天：没有做什么关于RM的事，一方面是四级，一方面是各种课程的最后阶段的作业和复习，一方面是学工程制图的CAD,这也是为什么这几天没有写日报的原因，因为没什么有用的东西能写

7.4
（重连）日报第三十一天：今天把C板里的IST8310和BMI088的程序写了，然后参考例程和其余网络资料把imu温度控制也写了，并对以上三个内容有一定的了解，今天还遇到了freeRTOS的堆栈溢出问题，之后要学习了解怎么处理freeRTOS堆栈溢出的问题，并加深对freeRTOS的应用

7.5
日报第三十二天：今天把bmi088和ist8310的数据融合进行姿态解算，但是遇到了读不了寄存器和调试进不去的情况，问题锁定在姿态解算的任务，然后还存在内存溢出的情况

7.6
日报第三十三天：今天再重看一下freeRTOS的内容，看看如何解决上面的问题

7.7
日报第三十四天：发现不是内存溢出造成的问题，主要是寄存器读不了，返回不了数据，没有解决

7.8
日报第三十五天：详细阅读bmi088和ist8310的手册，读写寄存器指令无误，初步判断应该是通信协议与时序已经延时函数有问题

7.9
日报第三十六天：借鉴C板开源代码，开写部分云台的代码

7.10
日报第三十七天：云台代码编写完成，部分因借鉴还无法理解，与底盘代码有异曲同工之处，另外为了方便理解与测试初步写的代码，云台的pid暂时独立开，以后再合并到通用pid代码中

7.11
日报第三十八天：结合C板开源代码理解整体的代码编写思路与代码运行功能

7.12~7.14
日报第三十九天到四十一天：金工实习和写金工实习报告

7.15~8.6
日报第四十二天到第六十四天:因为学车的原因，所以一天里面半天时间都是去掉了。这些天没有写日报原因还有就是每天看的东西也比较杂，主要看了硬件方面的东西，但都是比较基础的东西，另外学了学SW。
至于关于RM的，查阅学习了一下湖南大学，杭州电子科技大学，中国科学技术大学的开源电控代码和结构，见识了不同的写法，我觉得各有可取的地方，同时我觉得C板开源的结构也很好，可以加以提取其他队伍的开源代码来优化，现在有问题阻碍的是关于flash和ram溢出，内存管理是一个要注意的点。

8.7~8.9
日报第六十五天到第六七天：看了看几个不知名的开源框架，他们对于数据处理和滤波算法有一些想法，在研究研究

8.10
日报第六十八天：用MATLAB建立基本的速度环PID，然后参考了B站上的教程看看他们是怎么仿真和调试到想要的效果的，目前正在进行。
英雄和步兵的框架还没开始，今天稍微改了一下第一次底盘任务写的姿态解算代码，改掉一些C板开源的数据错误，因为我的想法是把这个我参照C板开源写的大部分都能移植到这个框架里，然后在移植的过程中，去掉一些我觉得C板开源里繁琐的传递数据之类的代码，变得简洁一点，接着要补注释和用上其他队伍开源里好的编写内容与方式。
