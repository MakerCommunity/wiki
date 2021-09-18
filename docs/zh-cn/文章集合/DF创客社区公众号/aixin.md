
# 跳动的爱心


![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153641.png ':size=50%')

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153655.png ':size=50%')

![跳动的爱心](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153707.png ':size=50%')


这个会根据捧着的人的心跳而跳动的“电子心脏”是焊武帝——jiripraus于妻子五周年纪念日制作的，为了感谢妻子多年来在背后的默默支持，体现了理工男特有的浪漫。

正如之前我们介绍过的那样，焊武帝的项目从来都不缺乏艺术感，这次也不例外。

心脏的外形用黄铜丝网制成。所有电子元器件都安全地隐藏在心脏内部，并由锂电池供电。

## 材料和工具

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/![](httpsimgkr.cn-bj.ufileos.com0fe28af2-335d-4dce-8150-b1bd5c3e755a.png).png )

### 材料

- 黄铜线1mm/5m
- 黄铜线0.8mm/5m
- 焊锡膏
- [3D打印心脏模型](https://www.cgtrader.com/free-3d-models/character/anatomy/love-low-poly "3D打印心脏模型"  ':size=50%')

STL和GCode文件，文末查看。

### 电子元器件

- Arduino NANO
- 锂电池充电器
- 锂电池
- MAX30102心率传感器
- Micro USB转换板
- 9个WS2812B型 RGB LED
- 迷你开关（MSK-12C02）

### 工具

- 3mm电烙铁头
- 钳子
- 剪线钳
- 镊子
- 双面胶带
- 还有一双巧手

## 3D打印模型

![3D打印心脏模型](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153758.png  ':size=50%')

利用提供的3D打印素材打印出心脏模型。

心脏比原始模型稍大，尺寸为100x84x49.5毫米。

为了节省时间和耗材，不需要设置太高的精度。这只是一个大致的模型。

模型文件见文末链接

## 焊接“外壳”


<div style="position: relative; padding: 30% 45%;">
<iframe 
    style="position: absolute; width: 100%; height: 100%; left: 0; top: 0;" 
    src="//player.bilibili.com/player.html?aid=242626525&bvid=BV1De411x7r4&cid=176417092&page=1" 
    scrolling="no" border="0" frameborder="no" framespacing="0" 
    allowfullscreen="true">
</iframe>
</div>

把焊台预热到270°C，准备好焊料和黄铜线。

开始在上一步中打印的塑料模型基础上焊接心脏的“外壳”。

这一步非常费时间，请不要着急。

选择心脏的一侧，然后将铜线放在3D模型的一侧开始。

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153819.png )

双面胶可以帮助你将铜线固定在适当的位置。

然后添加第二根铜线并把它们焊接在一起。添加第三根铜线，构成一个稳定的三角形结构。

注意使用焊锡膏让焊点焊点圆润一些。

继续重复焊接，直到正面已经完全焊接好。

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153838.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153854.png)


当铜线开始弯曲到另一面时停下来。

将3D打印的模型翻过来，然后重复上述步骤。

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153907.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153924.png)




千万记得把模型取出来后再把这两个面焊接到一起。

没有遇到意外的话，完成后大致是这个样子：

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153939.png)

## 电路图

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805153953.png)



心脏的“外壳”，现在已经做好了，接下来我们要为这颗美丽的心脏做一个“大脑”了。

内核是一个Arduino Nano微控制器，它通过I2C总线从MAX30102心率传感器模块读取脉冲数据。

视觉效果是由一组由Nano控制的9个可寻址WS2812b RGB LED实现。

电源由TP4056电池充电模块提供，该模块既可以通过锂电池为Arduino提供5V电压，又可以通过USB端口为电池充电。

尽管TP4056和Arduino Nano都有USB接口，但还需要一个额外的USB接口。这个接口将USB线分为TP4056处理的电源线和Arduino处理的数据线。否则，电路将无法工作。

## LED内芯

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154021.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154056.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154112.png)



![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154125.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154137.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154149.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154205.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154218.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154234.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154250.png)

接下来，让我们把这东西点亮！

我们要把内部的RGB LED做成心形。

这很简单。因此，不要犹豫，把他们焊接在一起，为最终组装部件做好准备。

#### 你可能需要：

- 纸板
- WS2812b RGB LED（9个）
- 0.8mm黄铜线

#### 步骤：

1.打印出模板并用双面胶粘住红色标记点。

2.把LED倒放在纸板的红色标记点上。明智的做法是制作接地和VCC引脚，以确保正确焊接。将接地引脚朝向心形的外圈。

3.将心形的外环弯曲并焊接到LED的GROUND引脚。

4.将心形的内环弯曲并焊接到LED的VCC引脚。

5.将LED连接成链-每个LED都有数据输入和数据输出引脚。如果将第一个LED数据输出引脚连接到下一个LED数据输入引脚，则创建了一条链，该链仅需一根导线即可控制。在每个LED之间使用短导线线。数据输入引脚与GROUND位于同一侧。

6.搭好之后可以适当用一些酒精擦拭清洁。

## 电子知识

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154306.png)

这将是最困难的部分，因为它将需要一些电子知识。

#### 为Arduino NANO供电

我实现的电路并不是最容易执行的电路，但对于制作“心脏”本身来说，这是却是最优雅的电路。如果发现它太难了，可以在本节末尾查看其他方法。

让我们开始使用锂电池为Arduino Nano供电。如果查看原理图，您会发现USB的电源线没有直接连接到Arduino Nano，而是通过一个TP4056电池充电模块旁路。这确保了电池可以正常充电，“心脏”可以通过开关关闭。

从Arduino Nano上拆下USB连接器并添加Micro USB分线板。如图所示，将数据线和地线连接回Arduino NANO。将分线板的中心与Arduino NANO对齐，这样看起来更美观一些。

将TP4056电池充电板与Arduino Nano底部的两根电线焊接在一起-将OUT +与Arduino板上的5V连接，并将OUT-连接至GND。我在Arduino Nano和电池充电板之间留出一块空间，预留给500mA的锂电池。现在，将USB分线板的电源连接到电池充电板上的IN +，最后将IN-连接到GND。通过电源开关将电池引至电池充电板上的B+（红线）和B-（黑线）焊盘。现在，可以尝试首次启动电路板。

##### 提示：
同时从Arduino UNO拆下电源LED。总是亮着让人心烦意乱。

##### 方案1：
你还可以在Arduino Nano板上使用USB构建。如果取消焊接电路板底部的整流二极管，则可以使用mini USB的5V进行焊接，它将不再为电路板供电。

##### 方案2：
你的心脏可以有两个USB，一个用于编程，另一个用于给电池充电。Arduino Nano和TP4056电池充电模块都有一个USB，您可以使用它们。它不是很简约，但是很简单。

##### 方案3：
如果你不需要电池供电的“心脏”，那可以省略多余的USB板和电源充电电路。

## 将“大脑”嵌入“心脏”


![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154323.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154337.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154349.png)



![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154403.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154415.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154441.png)



将内部心脏焊接到心脏外壳的下半部分。内心的外部导线是GND，外壳本身也将是GND。因此，使用一些短的黄铜线，把它放入心脏的确切中心，如图片所示。

现在，将上面准备好的电池与Arduino焊接到心脏的内部。根据需要使用尽可能多的铜线，以确保可以讲它们固定在心脏内部。再次使用USB板和外壳上的GND引脚作为将其焊接到心脏外壳的位置。不要把它焊接到心脏的内部铜线上！LED的内部导线为5V。

将内部LED心脏的内部导线连接至Arduino Nano的5V，并将第一个RGB LED的DATA-IN连接至引脚D12。

## 安装心跳传感器

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154454.png)

MX30102传感器可在用手指触摸时测量心跳和血压。在心形外壳的上半部焊接电路板。在板的两侧使用一个小开口。这些是GND，因为心壳也是GND。

确保你可以触摸板上的黑色小小元件-即传感器。

拿3根软的导线-我用的是弹簧形式的3mm绝缘变压器铜线，把它们焊接到MAX30102板上的SCL、SDA和VIN引脚，如下所示:

- SCL至A5引脚
- SDA至A6引脚
- VIN至5V引脚

以上是所有需要的电气连接。在将上下壳体焊接在一起之前。千万记得测试一下是否有效，否则之后不好修。


## 上传程序和测试

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154510.png)

将Arduino连接到计算机，并上传文章所附的程序。记得打开电源开关。

上传后，心跳传感器上的红色LED应该会被点亮。

如果你触摸它，LED会根据你的心跳开始闪烁。正确测量心跳可能需要15秒，所以如果不是即时的，不要担心。

## 完工！

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154524.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/20200805154538.png)

![](https://cdn.jsdelivr.net/gh/RalstonLiu/VsImage/images/![](httpsimgkr.cn-bj.ufileos.com362fd493-a180-4e83-9974-550f9d954b7a.jpg).png)

成功的话就可以吧上壳和下壳焊接在一起，并用一些酒精类清洁剂擦拭整个“心脏”，清除掉残留的焊剂。

喜欢[这个项目](https://www.instructables.com/id/Beating-LED-Heart/ "文章来源")的话，可以考虑在[Patreon](https://www.patreon.com/jiripraus "Patreon")上支持[Jiri Praus](www.jiripraus.cz "Jiri Praus个人网站")。



## 视频测试



[filename](https://mv.loll.cc/filebrowser/DF/Water%20Rocket%20-%20Data%20Visualizer%20Demo.mp4 ':include :type=video controls width=100%')



## 往期回顾

[听说创客们都收藏了这个网站……](https://mp.weixin.qq.com/s?__biz=MjM5MzUzODg2NA==&mid=2652152142&idx=1&sn=95c126f73a525078b1ad2d3d3e737a6c&chksm=bd7577118a02fe07937c2bb2763e48fa0f00e9d17321ae4a4ca1e9dafa8b8a9534a7fd5a8934&scene=21#wechat_redirect)

[自制的大疆S1战车来了！](https://mp.weixin.qq.com/s?__biz=MjM5MzUzODg2NA==&mid=2652152143&idx=1&sn=03c242dd560a7db795506da57c92e701&chksm=bd7577108a02fe0689ddd29f52372b7b748ee13bc9ab675bde44821bfb94e0b2de7a968f20dd&scene=21#wechat_redirect)

[手把手教你上手 HuskyLens 哈士奇人工智能摄像头](https://mp.weixin.qq.com/s?__biz=MjM5MzUzODg2NA==&mid=2652152118&idx=1&sn=67670611685e2e65fb96ec3377ef431e&chksm=bd7577698a02fe7fc14e3851c309a2870e1bbb2b8c873262e8f19ebd61463e10148c6cf6d734&scene=21#wechat_redirect)

[【福利】Arduino系列引脚大全](https://mp.weixin.qq.com/s?__biz=MjM5MzUzODg2NA==&mid=2652152018&idx=1&sn=53b55689e1bf81597306cfe752bab77c&chksm=bd75768d8a02ff9b76d26d169d675844bf8414d3a02e7ad3ae3ba057a01e8314eeba83547145&scene=21#wechat_redirect)

[1小时内做一个Otto机器人](https://mp.weixin.qq.com/s?__biz=MjM5MzUzODg2NA==&mid=2652152088&idx=1&sn=c26091234baa3fd64c40f103babf979a&chksm=bd7577478a02fe51908027c0d84798104651ff15f62adaf9dd6077c04eed5b2803b172d973ac&scene=21#wechat_redirect)

[拾色手电：颜色万千，只取一种](https://mp.weixin.qq.com/s?__biz=MjM5MzUzODg2NA==&mid=2652151867&idx=1&sn=eb73f5c6bd007c7a4fa8c180710c65af&chksm=bd7576648a02ff7288a8f1d465a3874d3476a94fa507a115eb11d63e418bfde2521d9b744848&scene=21#wechat_redirect)

[【小白福利】如何入门Arduino（上）](https://mp.weixin.qq.com/s?__biz=MjM5MzUzODg2NA==&mid=2652152064&idx=1&sn=c5b1279efacae8a7c8553c4a1f229676&chksm=bd75775f8a02fe492614b3029cb4cb11796d5a8fa2edec41456cc86bdc563a53750d39a9dcb1&scene=21#wechat_redirect)

[【小白福利】如何入门Arduino（下）](https://mp.weixin.qq.com/s?__biz=MjM5MzUzODg2NA==&mid=2652152089&idx=1&sn=89a6b16b145475c6d940ada1acec05f0&chksm=bd7577468a02fe50faae3a6594e7fe3c540f6308313943b065e5846ca7ccf855c02593a36fae&scene=21#wechat_redirect)