---

title: 重新搭建AD环境
date: 2023-01-05
author: mxmhub
cover: true
img: /image/AD环境搭建/100.png
summary: 重新搭建AD环境后，插件及参数的校正

categories: harware
tags:

  - AD插件
  - 环境搭建
  - 参数校正

---




### 1. LOGO脚本

下载链接1：[PCB Logo Creator](./AD插件/PCBLogoCreator.rar)

- 将准备好的文件【PCB Logo Creator】放在ADx根目录下，电脑C盘 > Program Files > Altium > ADx

 <img src=".//AD环境搭建/1.png" alt="图片1" style="zoom:100%;" />

- 打开方式： 文件 > 运行脚本 > 浏览 > 来自文件 > 根据以上文件路径 > 【PCB Logo Creator】 > 点击PCB Logo Creator.PrjScr > 打开 > RunConverterScript > 确定
 <img src=".//AD环境搭建/2.png" alt="图片2" style="zoom:67%;" />

### 2. 在PCB里绘制圆形螺旋走线脚本

下载链接2：[Altium 使用脚本程序绘制圆形螺旋走线的方法](./AD插件/Altium使用脚本程序绘制圆形螺旋走线的方法.rar)

- 将准备好的文件【SpiralTrackVer0.8】放在ADx根目录下，电脑C盘 > Program Files > Altium > ADx   【参考图片1】
- 注意打开方式： Search输入run  > 运行脚本 > 浏览 > 来自文件 > 根据以上文件路径 > 【SpiralTrackVer0.8】 > 点击SpiralTrack.PrjScr > 打开 > Main > 确定   【参考图片2】

### 3. GitHub BOM预览

下载链接3：[GitHub BOM预览](./AD插件/InteractiveHtmlBomForAD_master.zip)

- 将准备好的文件【InteractiveHtmlBomForAD-master > InteractiveHtmlBomForAD】放在ADx根目录下，电脑C盘 > Program Files > Altium > ADx（也可以放在其他位置）【参考图片1】
- 注意打开方式： 文件  > 运行脚本 > 浏览 > 来自文件 > 根据以上文件路径 > 【InteractiveHtmlBomForAD】 > 点击startWin > 确定 > GenerateBom 即可【参考图片2】

### 4. 原理图元器件NC标识

下载链接4：[HWScript_V5.0_Setup](./AD插件/HWScript_V5.0_Setup.zip)

- 安装：
1. 关闭AD软件
2. 解压HWScript_V5.0_Setup
3. 双击AltiumSetup_HW.exe
4. 再次打开AD软件即可

- AD任务栏会新增HWScript_V5.0
- 元器件NC: SCHNCSelectComponents
- 元器件解除NC: SCHDontNCSelectComponents

 <img src=".//AD环境搭建/4.png" alt="图片3" style="zoom:100%;" />

### 5. AD库

- 将AD库放在Libraries此文件夹内，电脑C盘 > 公用 > 公用文件 > Altium > AD18 > Library（放在此文件夹后，打开AD软件 > Properties > Libraries > 已安装 > 库相对路径  > 选择其AD库）

### 6. SCH表格

- 将准备好的表格放在Templates此文件夹内，电脑C盘 > 公用 > 公用文件 > Altium > AD18 > Templates（如果表格内有图片，一并放在此文件夹）
- 注意打开方式：设计 > 模板 > 通用模板





