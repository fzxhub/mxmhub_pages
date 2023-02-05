---
title: ADlayout 常用功能
date: 2023-01-02
author: mxmhub
cover: true
img: 
summary: 
categories: harware
tags:
  - AD
  - PCB
  - Layout
---

### ADlayout 常用功能
#### 1. 网络等长走线

- D+C  (对象类浏览器)在Net Classes项右击添加类（将需要网络等长的线通过‘>’添加到成员栏）；
- T+T+R /U+R 出现十字交叉；
- 点击需要等长的线，按Tab键；
- 点击源自网络，选定目标长度，勾选修剪目标长度，确定。

#### 2. 蛇形走线

- T+T+R  出现十字交叉；
- 点击需要等长的线，按Tab键；
- 点击源自网络或手动，选定目标长度，勾选修剪目标长度；
- 在样式 型 选（Mitered with Arcs）、最大振幅（圆的高度）；
- 让边缘变"圆" - 按快捷键 "2", 就会增大弧的半径, 增到最大就是 两个 1/4 的弧直连 就是一个 180度的半圆了，确定。

#### 3. 在PCB中元器件重叠或出现规则错误，没有绿色显示

- 在PCB编辑器，点击Tools>Designe Rule Check>Rules To Check>在线缆勾选对应的检查项  >  确定
![](/image/ADlayout/1.png)
<img src="/image/ADlayout/3.png" style="zoom:50%;" />  或   DXP>Preferences>PCBEditor>General>Editing Options勾选Online DRC
![](/image/ADlayout/2.png)
- 如果依然解决不了则重新创建一个PCB，将其复制，替代该文件，重新编译即可

#### 4. 差分对

- 在原理图将需要做差分对的2根线，用放置网络标签后缀xx_P、xx_N为一对，xx必须一致，在放置 > 指示 > 差分对 放置在2根线上，如下图 xx=A
![](/image/ADlayout/4.png)
- 或者在PCB手动添加，PCB > Differential Pairs Editor > 添加 >如下图差分对，在正网络、负网络选择需要使用差分对的线，名称可随意命名 > 确定
![](/image/ADlayout/7.png)
- 快捷键【D+C】> Differential Pairs Class > 右击添加类 > 修改名称 > 在非成员栏选中相关成员 > 放入成员栏  > 确定
![](/image/ADlayout/6.png)
- 快捷键【D+R】> Design Rules > Routing > Differential Pairs Routing > 设置相关参数 > 确定
![](/image/ADlayout/5.png)

#### 5. 多层板设计（叠层设计）
#####  AD18前版本

- 快捷键【D+K】或 设计 > 层叠管理器（Layer Stack Manager）> Add Layer（（Add Layer）添加阳层）> Add Layer（（Add Internal Plane）添加阴层）；
- 如下图中1所添加的为阴层、2为阳层、3 电源层比地层内缩20H（H：电源和地之间的介质厚度），如需给层命名，双击需要修改的层直接命名即可。
![](/image/ADlayout/8.png)

#####  AD18后版本

- 4处Stack Symmetry 栏取消打勾,作用：取消叠层对称。设置完后保存即可
![](/image/ADlayout/9.png)
> 四层板：最常用的信号叠层顺序为 Sig/Gnd | Power/Sig
> 六层板：较容易实现阻抗控制的信号叠层顺序 Sig/ Gnd/ Sig | Sig/ Power/Sig
> 六层板：还有一种结构不对称的叠层顺序经常用到： Sig/Gnd/Sig | Power / Gnd /Sig
> 六层板：还有一种结构不对称的叠层顺序经常用到： Sig/Gnd/Sig | Gnd / Power /Sig
> 八层板：对称结构 Sig/Gnd/Sig/Gnd | Power/Sig/Gnd/Sig
> 八层板：不对称结构Sig/Gnd/Sig/ Sig | Power/Sig/Gnd/Sig
> 十层板：对称结构 Sig/Gnd/Sig/Sig/Gnd | Gnd/Sig/Sig/Gnd/Sig
> 十层板：不对称结构 Sig/Gnd/Sig/ Power | Sig/Gnd/Sig/ Sig/Gnd/Sig
> 十二层板：信号顺序Sig/Gnd/Sig/Gnd/Sig/Gnd | Power /Sig/Gnd/Sig/Gnd/Sig

##### 注意
- 在层管理中，默认有顶层底层两层
- 顶层和底层主要是信号层
- 内电层（阴层）：内电层是整个完整的平面，是整个的覆铜的，是负片腐蚀，即有走线的地方是腐蚀掉的。可以做电源层，也可以做地层
- 中间层（阳层）：中间层可以作为走线来用，和普通的信号层没有什么区别，只是走线在内部，是正片腐蚀
- Sig:信号层
- 带状线：指线走在内垫层
- 微带线：指线走在表层（顶层和底层）

#### 6. 走线时，周围变暗或者变黑

快捷键【Control+D】> Dimmed Objects > 拖动滑条可更改周边的亮灭长度，如下图
![](/image/ADlayout/10.png)

#### 7. 走线、焊盘、铺铜等如何设置成半透明，现象如下图 

![](/image/ADlayout/11.png)
快捷键【Control+D】 > Tracks/Pads/Polygons(可根据情况选择)> 拖动滑条可更改周边的亮灭长度(通常情况下将滑条拖至最左边)，如下图所示
![](/image/ADlayout/12.png)

#### 8. 插入LOGO图片

将【PCB Logo Creator】文件拷贝到安装的根目录下
下载链接：[PCB Logo Creator](/image/ADlayout/PCBLogoCreator.rar)
![](/image/ADlayout/14.png)
在search框中输入 Run > 文件(F)>运行脚本 > 浏览 > 来自文件 > 找到logo文件 > Run ConverterScript > load > 选择图片 > Board Layer(选择要导入的层) > Scaling Factor(放大倍数) > Convert
<img src="/image/ADlayout/13.png" style="zoom: 50%;" />

#### 9. PCB网格设置

Properties > Grid Manager > 任意双击Grid Manager下方 > 设置精细、粗糙 > 确定
![](/image/ADlayout/15.png)

#### 10. 检查PCB布线是否连接完成，有无飞线

首先，快捷键【N】 > 显示连接（S） >  全部（A）
![](/image/ADlayout/16.png)
Properties > Board Information(板子信息) > Nets > Unrouted(飞线数量) > DRC Violations(DRC报错数量)
![](/image/ADlayout/17.png)

#### 11. 批量修改字符串位置
PCB Filter > 过滤 > 输入元器件（IsComponent）> 全部应用 > 选中需要修改的元器件 > 右击 > 对齐 > 定位器件文本 > 选择文本位置 > 确定
![](/image/ADlayout/18.png)

#### 12. 批量修改字符串和元器件的旋转方向一致

- 此处的字符串指 位号-Designator和参数-Comment
- 选中元器件 >  右击 > 查找相似对象 > 找到Rotation在第三栏将Any改成Same > 确认弹出
![](/image/ADlayout/19.png)
- Properties  >  单击需要修改的 (Designator or Comment)  > 在Rotation方框输入需要旋转角度值 > 回车即可
![](/image/ADlayout/20.png)
![](/image/ADlayout/21.png)

#### 13. 选中元器件摆放命令（矩形区域排列）

- 首先检查工具 > 交叉选择模式 是否开启
- 在原理图选中需要在PCB显示的元器件 > 工具 > 元器件摆放 > 在矩形区域排列 > 画个区域即可

#### 14. 自定义快捷键

以设置元器件摆放命令为例：在上方的菜单栏右击 > Customizing PCB Editor > 将需要定义快捷键的选项右击 > Edit > 快捷键 > 主要的（定义快捷键）> 确定
![](/image/ADlayout/22.png)
![](/image/ADlayout/23.png)

#### 15. 更新修改好的封装到PCB文件

PCB Librany > 选择对象 > 右击 > Update PCB With C0603(封装名)  或 Update PCB With All(全部) > 确定
<img src="/image/ADlayout/24.png" style="zoom:50%;" />

#### 16. PCB设置参考线

Properties > Guide Manager > Add > Add Horizontal Guide和Add Vertical Guide > 输入坐标值
![](/image/ADlayout/25.png)

#### 17. BGA扇出
- BGA封装外围两排引脚直接引线出去
- 选中BGA封装 > 右击 > 器件操作 > 器件扇出 > 勾选扇出完成后包含逃逸布线 > 确定

![](/image/ADlayout/26.png)

#### 18. 设置Xsignal-两根或多根线等长
- 创建Xsignal：将导线两端的焊盘选中 > 设计 > Xsignal > 以选中的管脚创建Xsignal > 创建两根为一组
- 运行Xsignal向导：设计 > Xsignal > 运行Xsignal向导 > next > Custom Multi-Component Interconnect > next > 选择连接一端的器件 > next > 标签（选择创建好的类）> next > 选择连接另一端的器件 > next > 可改变名称 > next > 点选不，我不想调整Xsignal的布线长度 > next > finish

#### 19. EMI干扰
- POWER 和GND内电层铺铜大小一样会产生一定的干扰，解决方法将POWER内电层铺铜减少20mil
- 设计 > 层叠管理器 > 在POWER内电层 > Pullback 20改成40 > OK

![](/image/ADlayout/27.png)

#### 20. 铺铜
方法1: 在机械层用线条画边框 > 选中边框 > 工具 > 转换 > 从选择的元素创建铺铜 > 双击选中的框内区域 > Properties > net（GND）> Properties(Layer)选择层 > Fill Mode（Solid (copper regions））> Pour Over All Same Net Objects > 勾选Remove Dead Copper > Apply

![](/image/ADlayout/28.png)

方法2: 直接点击放置多边形平面，然后将需要铺铜的区域选中，在Properties选择网络即可

方法3: 
- 工具 > 铺铜 > 铺铜管理器 > 来自......的新多边形 > 板外框 > 确定
- 在Top layer 铺铜块上双击 >  Properties > net（GND）> Properties(Layer)选择层 > Fill Mode（Solid (copper regions））> Pour Over All Same Net Objects > 勾选Remove Dead Copper > Apply

更新铺铜: 选中需要更新铺铜 > 右击 > 铺铜操作 > 重铺选中的铺铜 或 所以铺铜重铺

编辑铺铜: 选中需要编辑铺铜 > 右击 > 铺铜操作 > 调整铺铜边缘

铺铜挖空区域: 放置 > 多边形铺铜挖空 > 选中区域 > 即可

#### 21. 簇到板框的最小间距设置-10mil
- 设计 > 规则 > Manufacturing > Board Outline Clearance > 新建 > 最小间距 10mil > 应用 > 确定

![](/image/ADlayout/29.png)

#### 22. 泪滴 

- 添加：工具 > 滴泪 > 工作模式（添加）> 对象（所有）> 泪滴形式（Line）> 勾选强制铺泪滴 > 勾选（过孔/通孔100%、 贴片焊盘400%、 走线100%、 T型链接400%）> 确定
- 删除：工具 > 滴泪 > 工作模式（删除）> 确定

![](/image/ADlayout/30.png)

#### 23. 拼板操作
- 在当前工程下新建一个PCB > 放置 > 拼板阵列 > 按TAB键 > 在PCB Document 添加需要拼板的文件PCB > 打开 > column count (拼板数量横)，Row count(拼板数量竖)，column margin(拼板槽间距一般3mm),Row margin(同理间距) > 点击放置 > 现在自动同步 > 确定

![](/image/ADlayout/31.png)

> 注意：SMT一般厂家板子需要加工板框加宽5mm（工艺边），在机械1层，放置无电气属性过孔φ0.5-0.8mm，邮票孔数量放置5-8个，邮票孔边间距0.5mm，板槽间距2-3mm；
> 放置定位孔：φ2-3mm（非电气属性过孔）
> 放置mark点（光学定位）：φ1mm（封装的形式放置）

![](/image/ADlayout/32.png)

> 描画板框外形：（外扩距离设置：设计 > 规则 > Clearance > 最小间距 > 2-3mm）选中板框外形 > 复制到TOP/Botom Layer > 工具 > 描画选择对象的外形 > 将原本的外框线和外框内缩线删除（将间距类设置改回原来的设置）

![](/image/ADlayout/33.png)

特殊粘贴：选择需要复制的电路板 > 复制 > 编辑 > 特殊粘贴 > 勾选保持网络名称 和重复位号  > 粘贴

点击相关的视频链接： [特殊粘贴视频](https://www.bilibili.com/video/BV12x411d7NZ/?spm_id_from=333.788.videocard.0)

#### 24. 管脚/部件交换设置
自动交换：双击要编辑的器件 > swapping potions > 勾选Enable Pin Swapping > 工具 > 管脚/部件交换 > 点击该器件 > 配置元器件 > 全选 > 分配引脚交换群组依据 > 类型 > 确定

![](/image/ADlayout/34.png)
![](/image/ADlayout/35.png)

- 工具 > 管脚/部件交换 > 自动网络/管脚优化器 
- 手动交换：双击要编辑的器件 > swapping potions > 勾选Enable Pin Swapping > 工具 > 管脚/部件交换 > 电机该器件 > 配置元器件 > 全选 > 分配引脚交换群组依据 > 类型 > 确定
- 工具 > 管脚/部件交换 > 交互式管脚/网络交换 > 点击要交换的两个管脚
- 将交换部件/网络更新到原理图：设计 > Update Schematics in PCB_project1.prhpcb > 验证更新 > 执行变更 > 关闭

![](/image/ADlayout/36.png)

#### 25. 多层线路PDF输出设置

文件 > 智能PDF > Next > 当前文件 > Next > Next >在Name栏鼠标右击 >增加打印输出层（Insert Printout）（板子有几层，创建几个）> 点击修改名称   > 双击 选择需要的层 > Next > Next > Finish

![](/image/ADlayout/37.png)

#### 26. 装配PFD输出设置

装配PFD输出：文件 > 智能PDF > Next > 当前文件 > Next > Next >在Name栏鼠标右击 >创建装配图（Create Assembly Drawings）> 双击  >选择需要的层

![](/image/ADlayout/38.png)

#### 27. 装配DXF文件输出设置

装配DXF文件输出：先将绘制好的PCB复制一份 > 取消全部布线、删除所有铺铜和挖铜 > 文件 > 导出 > DCF/DWG > 选择保存路径 > 版本选择2004 > 格式选择DXF > 其他选择系统默认 > 确定

![](/image/ADlayout/58.png)

#### 28. 3D 模型导出设置
先在层叠管理器将板子的总厚度设为1.6mm左右，调整框内的参数

![](/image/ADlayout/40.png)

文件 > 导出 > STEP 3D > 选择保存路径 > 设置选择默认即可 > 确定

#### 29. PCB中如何关掉左上角坐标信号浮窗

- Shift+H

#### 30. PCB交叉选择模式中，如何设置只高亮元器件，元器件不跟随鼠标移动

设置 > Nacigation > 交叉选择模式 > 重新定位选中的PCB器件 > 将其的勾去掉

![](/image/ADlayout/41.png)

#### 31. 板子外框设置方式 

选择机械1层（Mechanical ）  > 选择放置线条  > 绘制出板边框形状（首尾封闭）并将其选中 > 设计 > 板子形状 > 按照选择对象定义

![](/image/ADlayout/42.png)

#### 32. AD软件不能查看GERBER文件

- 首先，打开AD软件 > 文件 > 新建 > CAM Document 
- 其次，文件 > 导入 > Gerber > 将所有Gerber文件全选打开 > 出现导入选项 > 点击OK即可

![](/image/ADlayout/43.png)

点击相关的视频链接： [图文链接](https://zhidao.baidu.com/question/457013016584730245.html )

#### 33. 倒角布线

先选中需要的的倒角 > 工具 > 转换 > 将选中导线转换为倒角 > 倒角角度输入 > 确定

![](/image/ADlayout/44.png)
![](/image/ADlayout/45.png)

#### 34. 过孔网络屏蔽工具

添加：选中需要屏蔽的网络 > 工具 > 缝合孔/屏蔽 > 添加网络屏蔽 > 1（要屏蔽的网络）2（需要屏蔽的网络间距）3（屏蔽孔之间的间距）5（屏蔽的参考网络选择）

![](/image/ADlayout/46.png)

#### 35. 移除/还原未使用焊盘工具 （过孔中间层设置）

- 移除：工具 > 移除未使用的焊盘 > Remove unused >确定
- 还原：工具 > 移除未使用的焊盘 > Restore unused >确定

![](/image/ADlayout/47.png)

#### 36. 区域块属性设置

多边形铺铜挖空：设置 > 多边形铺铜挖空 （Kind默认：Polygon Cutout）> 选择需要挖空的区域即可

![](/image/ADlayout/48.png)

多边形填充：设置 > 多边形铺铜挖空（Kind：Copper） > 选择需要填充的区域即可

![](/image/ADlayout/49.png)

#### 37. ROOM功能的使用

设计要求：天线与GND的焊盘使用全连接；天线与GND的铺铜间隔15MIL

![](/image/ADlayout/50.png)

设计 >  Room  > 放置ROOM（根据情况放置方框内其一种） > 单击 > 按下Tab键编辑 

![](/image/ADlayout/51.png)

设计 > 规则 > Design rules > plane > Polygon connect style > Where the first object matches(选择Custom query) > 查询助手 > PCB Functions > WithinRoom > 输入'名称' > 连接方式选择Direct connect

![](/image/ADlayout/52.png)

设计 > 规则 > Design rules > Electrical > Clearance > Where the first object matches(选择Custom query) > 查询助手 > 步骤同上  最小间距设为 15MIL

![](/image/ADlayout/53.png)

如需设计 ROOM内的线宽 步骤基本同上

![](/image/ADlayout/54.png)

注意：如若DRC编译报错，检查Where the object matches处是否为Components Class xx（元器件类），此处无特别设置，一定要包含ROOM内元器件

![](/image/ADlayout/55.png)

#### 38. 闭合回路设置
批量设置方法一：
工具 > 优先选项 > PCB Editor > Interactive routing > 勾选 自动移除闭合回路 >确定

![](/image/ADlayout/56.png)

批量设置方法二：
走线状态下 > TAB键 > Routing gloss effort > 选择 Automatically remove loops（自动移除闭合回路）

![](/image/ADlayout/57.png)

#### 39. 如何设置丝印和元器件的旋转方向一致

- 此处的丝印指 位号-Designator和参数-Comment
- 选中元器件 >  右击 > 查找相似对象 > 找到Rotation在第三栏将Any改成Same > 确认
- 弹出Properties  >  单击需要修改的 (Designator or Comment)  > 在Rotation方框输入需要旋转角度值 > 回车即可

![](/image/ADlayout/59.png)
<img src="/image/ADlayout/60.png" style="zoom:40%;" />

#### 40. PCB元器件封装焊盘去掉Top Paste and Top Solder层

Top Paste:  双击需要修改的焊盘 > Paste Mask Expansion > Manual > 在方框内填入负数即可

Top Solder: 双击需要修改的焊盘 > Solder Mask Expansion > Rule > Top 的 Tented方框内打勾

![](/image/ADlayout/61.png)

#### 41. PCB元器件封装焊盘去掉Top Paste and Top Solder层

选中需要修改的焊盘 > Properties > Offset From Hole Center(X/Y) > 在方框内输入需要调整的坐标位置

![](/image/ADlayout/62.png)