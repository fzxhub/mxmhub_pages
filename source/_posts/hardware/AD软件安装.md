---
title: AD软件安装及卸载
date: 2022-11-30
author: mxmhub
cover: true
img: 
summary: AD软件安装及卸载
categories: hardware
tags:
  - AD
  - 安装
---


### 软件安装及卸载
#### 软件安装
1. 解压文件，双击AltiumDesignerSetup_21_0_3.exe 文件， 即可弹出安装向导对话框， 点击NEXT
<img src="/imageAD软件安装/1.png" style="zoom:115%;" />
<img src="/image/AD软件安装/2.png"  />
2. 选择中文安装语言，并观看协议，选择接受协议内容
<img src="/image/AD软件安装/3.png" style="zoom:115%;" />
<img src="/image/AD软件安装/4.png" style="zoom:115%;" />
3. 继续单击向导欢迎窗口的“Next”按钮，显示如图所示安装功能选择对话框，选择需要安装的组件功能。一般选择安装图示箭头指示的“PCB Design”、Importers\Exporters 两项即可
<img src="/image/AD软件安装/5.png" style="zoom:115%;" />
4. 继续单击向导欢迎窗口的“Next”按钮，显示如图所示选择安装路径对话框，选择安装路径和共享文件路径，推荐使用默认设置的路
<img src="/image/AD软件安装/6.png" style="zoom:115%;" />
5. 确认安装信息无误后，继续单击对话框的“Next”按钮，安装开始，等待5～10 分钟，安装即可完成，有些用户电脑应配置要求，会自动安装“Microsoft NET4.6.1”插件，安装之后重启电脑或者会出现如图所示安装完成界面，表示安装成功
<img src="/image/AD软件安装/7.png" style="zoom:115%;" />
<img src="/image/AD软件安装/8.png" style="zoom:115%;" />
6. 软件和谐破解
先准备好相关的2个文件：分别是“shfolder.dll”文件和Licenses “xxxx.alf” 文件
<img src="/image/AD软件安装/9.png" style="zoom:115%;" />
7. 把shfolder.dll 文件复制并粘贴到安装目录中下，一般默认路径的话是一下路径：C:\Program Files\Altium\AD21
8. 安装目录下找到“X2.exe”文件，双击打开Altium 21 软件
<img src="/image/AD软件安装/10.png" style="zoom:115%;" />
9. 右上角点击头像图标，然后选择命令“License Management...”，出现如图所示账户窗口界面
<img src="/image/AD软件安装/11.png" style="zoom:115%;" />
<img src="/image/AD软件安装/12.png" style="zoom:115%;" />
10. 找到Add standalone license file，弹出加载license 文件对话框， 加载我们提供的和谐Licenses 文件（后缀.alf）
<img src="/image/AD软件安装/13.png" style="zoom:115%;" />
11. OK， 我们软件和谐就到此为止了， 如果你能新建PCB 或者原理图了就标示破解成功了。效果如图：
<img src="/image/AD软件安装/14.png" style="zoom:115%;" />
12. 软件汉化：打开软件，右上角执行图标命令“ <img src="/image/AD软件安装/16.png" style="zoom: 60%;" />”，点击勾选“Use Localized resources”，
这个时候会提示一个让您重启软件的提示，您吧软件关掉重新打开就可以是汉化
版本了，如果您想再次切换到英文版，可以按照相同的操作再处理一遍
<img src="/image/AD软件安装/15.png" style="zoom:115%;" />
#### 软件卸载
1. 控制面板 > 程序 > 程序和功能 > 卸载程序 > 找到AD软件 > 选中右击卸载
<img src="/image/AD软件安装/21.png" style="zoom:115%;" />
2. 一直next，直到结束
<img src="/image/AD软件安装/22.png" style="zoom:115%;" />
3. 按Win+R > 输入regedit > 确定
<img src="/image/AD软件安装/23.png" style="zoom:115%;" />
4. 将注册表的第二项“HKEY_CURRENT_USER”和第三项“HKEY_LOCAL_MACHINE”，里面的子文件夹“SOFTWARE”中的“Altium”删除即可
> 注意：两项中的都要删掉才行

<img src="/image/AD软件安装/24.png" style="zoom:100%;" />