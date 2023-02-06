---

title: AD通用设置
date: 2023-01-05
author: mxmhub
cover: true
img: /image/ADgeneral/100.png

summary: sch、pcb的参数设置,sch项目检查、pcb规则设计,文件输出等功能均在本章有所介绍

categories: harware
tags:
  - AD
  - SCH
  - PCB
  - 参数设置

---

### 1. 原理图参数表设置

#### 1.1 原理图表格模板样式

- 如下图:

![原理图模板](/image/ADgeneral/1.png)

- 模板设置：设计 > 模板> 通用模板> 选择合适纸张大小的模板
- 参数设置：右上角搜索（Search） > 选项 > 文档参数 > 在 Parameters 栏修改对应参数 或 Properties > 在 Parameters 栏修改对应参数

#### 1.2 原理图工程编译检查设置

- 工程 > 工程选项 > 位号重复（Duplicate Paet Designators）、重复名称（Duplicate nets）、网络悬浮（Floating net labels）、电源悬浮（Floating power objects）、单端网络（Nets with only one pin）将这五个都改成严重错误（Fatel Error）

![](/image/ADgeneral/2.png)

![](/image/ADgeneral/3.png)

原理图编译完成后一般用鼠标点击 Messages 中的最后一项，如果显示重复号高亮电源和地，说明原理图短路

![](/image/ADgeneral/4.png)

### 2. PCB规则设计-间距

#### 2.1 板框间距:

- 板框间距: 推荐值为0.3mm,最小间距值为 0.1mm
- 非邮票孔处走线和焊盘距板边距离≧0.3mm
- 非邮票孔处锣边公差：±0.2mm（普锣），±0.1mm（精锣）

![](/image/ADgeneral/5.png)

方法2:  此方法可以不添加Keep-out layer

最小间距值为到板框距离值

![](/image/ADgeneral/29.png)

#### 2.2 ROOM间距

ROOM间距: 最小间距值为 0.089mm(3.5mil),推荐值根据设计需求写

如图此ROOM为天线的ROOM,天线阻抗为50R,根据阻抗计算得此信号与其他信号间距为0.381mm

![](/image/ADgeneral/6.png)

其他ROOM设计可参考此图

#### 2.3 Polygon间距

Polygon间距: 最小间距值为 0.089mm(3.5mil),推荐值根据设计需求写

![](/image/ADgeneral/7.png)

此设计一般针对阻抗信号,如共面阻抗90R等

#### 2.4 DifferentialPair 间距

DifferentialPair 间距: 最小间距值为 0.089mm(3.5mil),推荐值根据设计需求写

![](/image/ADgeneral/8.png)

此设计一般针对阻抗信号,如共面阻抗100R等

#### 2.5 CLASS间距

CLASS间距: 推荐值为0.178mm(7mil)或0.2mm(8mil),最小间距值为 0.089mm(3.5mil)

![](/image/ADgeneral/9.png)

#### 2.6 ALL间距

ALL间距: 最小间距值为 0.089mm(3.5mil),推荐值根据设计需求写

![](/image/ADgeneral/10.png)

> 规则中优先级设置

> ![](/image/ADgeneral/11.png)

### 3. PCB规则设计-线宽

#### 3.1 ROOM线宽

ROOM线宽: 最小线宽值为 0.089mm(3.5mil),推荐值根据设计需求写

如图此ROOM为天线的ROOM,天线阻抗为50R,根据阻抗计算得此信号的线宽值为0.508mm(20mil)

![](/image/ADgeneral/12.png)

其他ROOM设计可参考此图

#### 3.2 CLASS线宽

CLASS线宽: 最小线宽值为 0.089mm(3.5mil),推荐值根据设计需求写

![](/image/ADgeneral/13.png)

此设计一般针对阻抗信号,如单端阻抗50R等

#### 3.3 ALL线宽

ALL线宽: 最小线宽值为 0.089mm(3.5mil),推荐值根据设计需求写

![](/image/ADgeneral/14.png)

### 4. PCB规则设计-过孔

- 单双面板：0.3mm(内径)/0.5mm(外径)
- 多层板：0.15mm(内径)/0.25mm(外径)

![](/image/ADgeneral/16.png)

#### 4.1 CLASS过孔

CLASS过孔: 推荐值根据设计需求写

![](/image/ADgeneral/15.png)

#### 4.2 ROOM过孔

ROOM过孔: 推荐值根据设计需求写

![](/image/ADgeneral/17.png)

#### 4.3 ALL过孔

ALL过孔: 推荐值根据设计需求写

![](/image/ADgeneral/18.png)

### 5 PCB规则设计-DifferentialPair线宽

DifferentialPair线宽: 推荐值根据设计需求写

![](/image/ADgeneral/19.png)

### 6 PCB规则设计-Plane

#### 6.1 Power Plane Connect Style

Power Plane Connect Style(电源平面连接方式或负片连接方式): 推荐设置 Ddirect Connect

![](/image/ADgeneral/20.png)

#### 6.2 Power Plane Clearance

Power Plane Clearance(电源平面层间距或负片连接间距): 推荐值为0.178mm(7mil)

![](/image/ADgeneral/21.png)

#### 6.3 ROOM铺铜

ROOM铺铜: 推荐设置根据设计需要选择

![](/image/ADgeneral/22.png)

#### 6.4 Footprint铺铜

Footprint铺铜: 推荐设置根据设计需要选择

此设计是以封装名的类型设置铺铜连接方式

![](/image/ADgeneral/23.png)

#### 6.5 ALL铺铜

ALL铺铜: 推荐设置根据设计需要选择

此处的通孔和SMD一般选择 Relief Connect,过孔一般选择Ddirect Connect

![](/image/ADgeneral/24.png)

### 7 PCB规则设计-Manufacturing

#### 7.1 Hole Size(孔的大小)

Hole Size(孔的大小): 此处最大的值若小于实际使用到的孔的值,DRC则会报错

注意: 此设计含孔与过孔

![](/image/ADgeneral/25.png)

#### 7.2 HoleToHoleClearance(孔到孔间距)

HoleToHoleClearance(孔到孔间距): 推荐值根据设计需求写

![](/image/ADgeneral/26.png)

#### 7.3 MinimumSolderMaskSliver(最小化阻焊层裂口)

MinimumSolderMaskSliver(最小化阻焊层裂口): 推荐值根据设计需求写

![](/image/ADgeneral/27.png)

#### 7.4 SilkToSilkClearance(对象与丝印层的最小距离)

SilkToSilkClearance(对象与丝印层的最小距离): 推荐值根据设计需求写

![](/image/ADgeneral/28.png)

#### 7.5 BoardOutlineClearance(板框最小距离)

- BoardOutlineClearance(板框最小距离): 推荐值为0.3mm,最小间距值为 0.1mm
- 非邮票孔处走线和焊盘距板边距离≧0.3mm
- 非邮票孔处锣边公差：±0.2mm（普锣），±0.1mm（精锣）

![](/image/ADgeneral/29.png)

### 8 PCB规则设计-Length(等长线)

Length(等长线): 根据同组类需要同等长度设置等长区间

例如:DDR中的数据线D0-D15需要将等长控制在1600-1700mil,误差在100mil内

![](/image/ADgeneral/31.png)

其他参数类设置可参考此图

### 9 PCB规则设计-Placement

#### 9.1 RoomDefinition(ROOM参数设置

RoomDefinition(ROOM参数设置):根据设计需求设置Where The Object Matches

![](/image/ADgeneral/32.png)

#### 9.2 ComponentClearance (组件间隙)

允许组件与组件的最小间距值设置,此设计预防撞件

![](/image/ADgeneral/33.png)

#### 9.3 Height (组件允许高度)

允许组件的高度值设置,此设计预防与其他干涉

![](/image/ADgeneral/34.png)

### 10. 板子形状剪切设置

- 设置参考坐标原点：编辑 > 原点 > 设置 > 点击左下角，如下图中的 4
点击机械层（Mechanical 1）> 放置 > 线条 > 绘制板子的大小，如下图中的
2 和 3
- 选中所有边框,板框要首位封闭连接（下图中 2）> 设计 > 板子形状 > 按照选择对象定义 > 
板子颜色设置如下图中 1 > 选择颜色即可

![](/image/ADgeneral/35.png)

### 11. 铺铜设计

方法1: 在机械层用线条画边框 > 选中边框 > 工具 > 转换 > 从选择的元素创建铺铜 > 双击选中的框内区域 > Properties > net（GND）> Properties(Layer)选择层 > Fill Mode（Solid (copper regions））> Pour Over All Same Net Objects > 勾选Remove Dead Copper > Apply

![](/image/ADgeneral/36.png)

方法2: 直接点击放置多边形平面，然后将需要铺铜的区域选中，在Properties选择网络即可

方法3: 
- 工具 > 铺铜 > 铺铜管理器 > 来自......的新多边形 > 板外框 > 确定
- 在Top layer 铺铜块上双击 >  Properties > net（GND）> Properties(Layer)选择层 > Fill Mode（Solid (copper regions））> Pour Over All Same Net Objects > 勾选Remove Dead Copper > Apply

更新铺铜: 选中需要更新铺铜 > 右击 > 铺铜操作 > 重铺选中的铺铜 或 所以铺铜重铺

编辑铺铜: 选中需要编辑铺铜 > 右击 > 铺铜操作 > 调整铺铜边缘

铺铜挖空区域: 放置 > 多边形铺铜挖空 > 选中区域 > 即可

### 12. 装配输出

#### 12.1 装配PFD输出

文件 > 智能 PDF > Next > 当前文件 > Next > Next >在 Name 栏鼠标右击 >创建装配图（Create Assembly Drawings）> 双击 >选择需要的层

![](/image/ADgeneral/37.png)

![](/image/ADgeneral/38.png)

#### 12.2 装配PFD输出装配DXF文件输出 

先将绘制好的PCB复制一份 > 取消全部布线、删除所有铺铜和挖铜 > 文件 > 导出 > DCF/DWG > 选择保存路径 > 版本选择 2004 > 格式选择 DXF > 其他选择系统默认 > 确定

<img src="/image/ADgeneral/39.png" style="zoom:80%;" />

使用AD20后版本重新编辑

![](/image/ADgeneral/55.png)

### 13. 制造文件导出

#### 13.1 Gerber Files文件导出
- 文件 > 制作输出 > gerber files > gerber设置 > 通用 > 单位（选择英寸）> 格式（选择 2:5）

![](/image/ADgeneral/40.png)

- 层 > 出图层 > 出图 > 可勾选 全选或选择使用的 > 镜像层 > 全部去掉

![](/image/ADgeneral/41.png)

- 钻孔图层: 勾选输出所有使用的钻孔对 和 勾选输出所有使用的钻孔

![](/image/ADgeneral/42.png)

- 光圈/高级> 默认设置

#### 13.2 NC Drill Files(钻孔文件导出)

- 文件 > 制作输出 > NC Drill files > NC Drill 设置 > 
NC Drill 格式 >> 单位（英寸）>> 格式（2:5）> 前导/尾数零（摒
弃尾数零）>> 坐标位置（参考相对原点）> 其他（优化变更位置
命名）

<img src="/image/ADgeneral/43.png" style="zoom: 80%;" />

默认设置,确定即可

![](/image/ADgeneral/44.png)

#### 13.3 钢表比对

- 文件 > 制作输出 > Test Point Report > 报告格式只勾选（IPC-D-356A）>其他采用默认

![](/image/ADgeneral/45.png)

#### 13.4 贴片坐标文件

- 文件 > 装配输出 > Generates pick and place files > 根据需求在所有列中勾选需要显示的项

![](/image/ADgeneral/46.png)

#### 13.5 导出的文件默认路径

导出的文件可在本工程中的 Project Outputs for vboost 文件夹内找到

![](/image/ADgeneral/47.png)

#### 13.6 文件夹管理

![](/image/ADgeneral/48.png)

- ASM：装配图（装配 PDF 输出文件（只包含 PCB 顶/底层内容）

![](/image/ADgeneral/49.png)

-  CAM：gerbera 文件夹（输出四种文件：gerber files、NC Drill、Test Point Report、Generates pick and place files）
-  Top Overlay 顶层丝印层、Top Paste 顶层钢网层、Top Solder 顶层阻焊层、Top 顶层线路层、Keep Out Layer 禁止布线层、Pick place for demo.txt 坐标文件

![](/image/ADgeneral/50.png)

-  DATASHEET：数据手册

![](/image/ADgeneral/51.png)

-  DXF：架构图

![](/image/ADgeneral/52.png)

- PRJ：工程文件夹

![](/image/ADgeneral/53.png)

- SMT：贴片文件（顶底层开钢网+坐标文件+装配图）

![](/image/ADgeneral/54.png)

> **注意:**
> 给贴片厂生产发 SMT 文件夹
> 给厂家制作 PCB 电路板发 CAM 文件夹
> 给结构工程师发 DXF 文件夹

