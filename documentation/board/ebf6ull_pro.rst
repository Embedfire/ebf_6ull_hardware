.. vim: syntax=rst


EBF6ULL Pro底板硬件手册
==========================================

可直接点击页面右上角的“Edit on github”到github下载整个仓库，仓库中包含以下所有硬件资料。


资料下载
------------------------

============  ====================
内容            下载链接
============  ====================
硬件原理图     :download:`野火_EBF6ULL S1 Pro 底板_原理图.pdf <../../hardware/EBF6ULL S1 Pro/野火_EBF6ULL S1 Pro 底板_原理图_20200729.pdf>`
机械尺寸图     :download:`野火_EBF6ULL S1 Pro 底板_机械尺寸.pdf <../../hardware/EBF6ULL S1 Pro/野火_EBF6ULL S1 Pro 底板_V1.0_机械尺寸.pdf>`
装配图         :download:`野火_EBF6ULL S1 Pro 底板_装配图.pdf <../../hardware/EBF6ULL S1 Pro/野火_EBF6ULL S1 Pro 底板_装配图_20200926002.pdf>`
封装库         :download:`野火_EBF6ULL S1 Pro 底板_封装库.zip <../../hardware/EBF6ULL S1 Pro/封装库/封装库.rar>`
============  ====================

============  ====================
内容            下载链接
============  ====================
硬件原理图     :download:`野火_EBF6ULL B1 Pro_底板_原理图.pdf <../../hardware/EBF6ULL B1 Pro/野火_EBF6ULL B1 Pro 底板_原理图.pdf>`
机械尺寸图     :download:`野火_EBF6ULL B1 Pro 底板_机械尺寸.pdf <../../hardware/EBF6ULL B1 Pro/野火_EBF6ULL B1 Pro 底板_机械尺寸.pdf>`
装配图         :download:`野火_EBF6ULL B1 Pro 底板_装配图.pdf <../../hardware/EBF6ULL B1 Pro/野火_EBF6ULL B1 Pro 底板_装配图.pdf>`
封装库         :download:`野火_EBF6ULL B1 Pro 底板_封装库.zip <../../hardware/EBF6ULL B1 Pro/封装库/封装库.rar>`
============  ====================

============  ====================
内容            下载链接
============  ====================
硬件原理图     :download:`野火_EBF6ULL F1 Pro_底板_原理图.pdf <../../hardware/EBF6ULL F1 Pro/野火_EBF6ULL F1 Pro 底板_原理图.pdf>`
机械尺寸图     :download:`野火_EBF6ULL F1 Pro 底板_机械尺寸.pdf <../../hardware/EBF6ULL F1 Pro/野火_EBF6ULL F1 Pro 底板_机械尺寸.pdf>`
装配图         :download:`野火_EBF6ULL F1 Pro 底板_装配图.pdf <../../hardware/EBF6ULL F1 Pro/野火_EBF6ULL F1 Pro 底板_装配图.pdf>`
封装库         :download:`野火_EBF6ULL F1 Pro 底板_封装库.zip <../../hardware/EBF6ULL F1 Pro/封装库/封装库.zip>`
============  ====================

产品概述
------------------------

EBF6ULL S1 Pro开发板是野火电子基于NXP i.MX 6ULL系列处理器设计的一款低功耗单板电脑，
工业级主频最高可达 792MHz，具体如下图。

.. image:: media/imx6pr002.jpeg
   :align: center
   :alt: EBF6ULL S1 Pro开发板



EBF6ULL S1 Pro开发板提供完整的SDK驱动开发包、核心板封装库，底板应用参考设计原理图，
可帮助客户大大缩减产品的开发时间，加快产品上市。目前提供Linux 4.1.15版本的内核，配套的系统自带python、Qt等组件。

开发板整板由EBF6ULL S1核心板模组和底板组成，元件采用工业级选料，
其中核心板板载主控芯片512MB DDR3L内存，256/512MB Nand-FLASH（或8GB eMMC）。

配套的核心板说明见《:doc:`ebf6ulls1`》



EBFULL Pro底板硬件资源
------------------------

野火EBF6ULL Pro底板硬件资源见图：

.. image:: media/imx6pr005.jpeg
   :align: center
   :alt: EBF6ULL Pro底板硬件资源见图


EBF6ULL S1 Pro底板硬件资源表：

============ ============================================================================================
尺寸         200*13.5MM
PCB          2层、黑色沉金
\
DC12V 接口   DC 12V@2A 直流输入，不支持电脑USB供电，因为电流不够
USB转串口    使用MiniUSB接口，使用CH340驱动
KEY          RESET 1个，ONOFF 1个，WAKEUP 1个，MODE1个
RGB灯        由三个独立的R、G、B小灯组成
六轴陀螺仪   型号MPU6050
DB9接口      2路，1路母头DB9，1路公头DB9，使用RS232协议
485接口      2路，2线接线柱引出， 使用RS485协议
CAN接口      2路，2线接线柱引出 ，使用CAN协议
EBF接口      1个，使用1*6P 2.54间距排母引出，适用于连接使用串口协议的小模块
启动配置     通过1个8位的拨码开关配合实现
以太网       2路百兆以太网，型号KSZ8081RNB
SPDIF收发    1x SPDIFIN，DLT-1150光纤座；1x SPDIFOUT，DLR-1150光纤座，用于音频光纤输入输出
JTAG接口     1个，使用2*5P 2.54间距牛角座引出
音频接口     1x LINE IN，3.5mm音频座；1x LINE OUT，3.5mm音频座；1x MIC IN，电容咪头，使用WM8960编解码芯片
环境光传感器 型号AP3216C
红外接收     型号HS1838
温湿度接口   可接入DHT11/DS18B20传感器
喇叭接口     1x4p XH2.0接口引出，可用型号：3080
摄像头接口   可直接配套野火OV5640摄像头
蜂鸣器       有源蜂鸣器，3.3V驱动
USB HOST     4路通过芯片原生外扩，A型母座双层USB接口
电位器       1K阻值变动
micro USB    原生引出，支持OTG
RTC座子      电池座，适用电池型号CR1220
WIFI&蓝牙    型号：AP6236，不能与SD卡同时使用
SD卡座       microSD卡卡座，支持SD3.0，不能与WIFI同时使用
电容按键     可检测到触摸开关状态
HDMI接口     RGB转HDMI
LVDS接口     RGB转LVDS，通过2x15P 2.0间距排针引出
LCD接口      FPC接口，RGB888及I2C触摸信号，支持直接连接野火的5寸/7寸/4.3寸屏
GPIO         通过两排2*40P的2.54间距排针引出，可自主连接各种外部设备
============ ============================================================================================
