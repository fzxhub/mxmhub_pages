---
title: AD原理图设置
date: 2023-01-05
author: mxmhub
cover: true
img: 
summary: 
categories: harware
tags:
  - AD
  - 原理图
---


##### 1. 3D图纸（三维图纸）Draftsman

在工程下添加机械图纸 > 新建 > Draftsman Document > ok > Place > 

![](/image/ADsch/1.png)

生成后为主视图 > 双击主视图 > Properties > View side(可选前后左右视图) > 保存 > file > Expore to PDF > 装配图

![](/image/ADsch/3.png)

点击相关的视频链接：[Draftsman](<https://www.altium.com.cn/webinars/on-demand/altium-designer-18-%E6%96%B0%E5%8A%9F%E8%83%BD-draftsman-%E6%96%87%E6%A1%A3%E5%A4%84%E7%90%86%E6%8A%80%E6%9C%AF?utm_source=ownedmediawebinars&utm_medium=webinarsmegamenu&utm_campaign=webinars>
)

##### 2. 快速添加引脚和修改引脚名称

- 放置引脚 > 右击复制 > 编辑 > 阵列式粘贴 > 根据需要的引脚数量填写对象数量 > 勾选移除前导零 > 确定
- 选中所以引脚 > Panels(右下角) > SCHLIB List > View改为Edit > 将在Excel表格中引脚名称复制 > 在Name栏 > 右击 > 选择列 > 粘贴

![](/image/ADsch/4.png)

##### 3. 片断摘取连接

- 将需要摘取模块单独放在一个工程（片断摘取成功后可将工程删掉），原理图及PCB，在原理图将元器件编号起始值为1000，步骤：工具 > 注释 > 原理图标注 > 原理图页标注（起始索引）勾选并改值为1000 > Reset All > 更新更改列表 > 接受更改 > 确定，将此原理图导入PCB 

![](/image/ADsch/5.png)

- 选中片断摘录部分 > 右击 > 片断 > 从选择的对象创建片段 > 可修改名称和注释 > 确定

![](/image/ADsch/6.png)

- 如果将类似此对的片段加入原理图和PCB需要以下步骤：在PCB中 > 工程 > 元器件关联 > 通过匹配添加配对 > 执行更新 > 确定 ，在原理图中 > 工具 > 注释 > 原理图标注 > 原理图页（只勾选放入片断的原理图页）> Reset All > 更新更改列表 > 接受更改 > 确定，在导入PCB即可

点击相关的视频链接：[片断摘取连接](https://altiumvideos.live.altium.com.cn/#Detail/1222)

点击相关的图文链接：[片断摘取连接](https://www.altium.com/cn/documentation/altium-designer/designing-for-reuse?version=18.1)

##### 4. 同一个工程下有多个原理图和多个PCB

![](/image/ADsch/7.png)

工程 > 显示差异 > 选中要导入的PCB > 勾选高级模式 > 在左右侧栏中选中对应的原理图和PCB > 确定

![](/image/ADsch/8.png)

Extra Components栏鼠标右击 > Update All in >>PCB Document[PCB2.PcbDoc] > 创建工程变更列表 > 验证变更 > 执行变更 > 关闭

![](/image/ADsch/9.png)

##### 5. 原理图工程编译检查设置

原理图工程编译检查设置：工程 > 工程选项 > 位号重复（Duplicate Paet Designators）、网络悬浮（Floating net labels）、电源悬浮（Floating power objects）、单端网络（Nets with only one pin）将这四个都改成严重错误（Fatel Error）

![](/image/ADsch/10.png)
![](/image/ADsch/11.png)

##### 6. 绘制原理图库元器件如何添加子部件

- 添加新建一个元器件
- 可绘制完成一个子部件或在空白处右击 > 工具 > 新部件

![](/image/ADsch/12.png)

##### 7. 原理图模板设计

- 新建原理图 > Properties > Page options > Standard > 去掉勾Title block 
- 在原理图中放置 线 > 绘制自己想要的模板格式
- 按P+T（字符串添加）> 双击可改变其内容，颜色，字体大小
- 自动变量设置 > Properties > Properties > Text >将字符串改成*后定义自变量如下图：

![](/image/ADsch/13.png)

- 插入图片 > 放置 > 绘图工具 > 图像（插入准备好的图片）
- 保存此文件时，注意后缀改为 .schdoc 格式
- 将此文件放置到安装目录下即可

![](/image/ADsch/14.png)

##### 8. 元器件隐藏引脚连接到指定网络设置

> AD18版本前设置方法

![](/image/ADsch/15.png)

> AD18版本后设置方法

1) 首先在你的元件封装工程中，单击原理图库。这样把当前视窗内容切换到原理图库

![](/image/ADsch/16.png)

2) 在AD18后的窗口右下角找到“Pannels”->"SCH Library"。打开元件原理图库
- 或者可以在菜单中找到“视图”->"面板"->"SCH Library"
- 以74LS00为例：

![](/image/ADsch/17.png)

3) 双击74LS00。打开这个74LS00的属性。
- PS：这个74LS00是之前制作好的。其中两个（7，14引脚）分别接VCC和GND现在将其隐藏，使其在PCB工程中自动连接到对应网络
4) 如果你已经隐藏了引脚，必须看这一步骤。现在点击上图中的"Pin"卡片选项。进入引脚管理器，把隐藏的引脚，都显示出来

![](/image/ADsch/18.png)

5) 在AD18后的窗口右下角找到“Pannels” > “SCHLIB List”。打开元件原理图库列表
- 如果SCHLIB List中没有显示任何引脚信息

![](/image/ADsch/19.png)

- 选中需要需要编辑的引脚

![](/image/ADsch/20.png)

- 1勾选为隐藏，2编辑隐藏引脚连接到的指定网络（双击即可修改）

![](/image/ADsch/21.png)

##### 9.  添加原理图库引脚名称放置方式
> AD18版本前

双击需要修改的引脚 > Orientation > 选择模式（90 Degrees / 0Degrees）> 确定

![](/image/ADsch/22.png)

> AD18版本后

选中需要修改的引脚 > 窗口右下角找到“Pannels” > “SCHLIB List”> 在菜单栏右击 > switch to View mode > Pin name position mode(选择Custom) > pin name orientation > 选择模式（90 Degrees / 0Degrees）> 确定

![](/image/ADsch/23.png)

##### 10.  网络颜色同步

- 添加：视图 > 设置网络颜色 > 选择颜色（也可以自定义颜色）> 选择需要同步的网络即可

![](/image/ADsch/24.png)

- 删除：视图 > 设置网络颜色 > 清除网络颜色 > 选择需要删除的网络即可
- 同步到PCB：设计 > 编译到PCB即可

![](/image/ADsch/25.png)

















