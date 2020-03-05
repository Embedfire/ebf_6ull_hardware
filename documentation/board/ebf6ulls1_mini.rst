.. vim: syntax=rst


EBF6ULL S1 mini底板数据手册
==========================================

可直接点击页面右上角的“Edit on github”到github下载整个仓库，仓库中包含以下所有硬件资料。



资料下载
------------------------

=====================  ====================
内容                    下载链接
=====================  ====================
硬件原理图              :download:`野火_EBF6ULL S1 Mini 底板_V1.0_原理图.pdf <../../hardware/EBF6ULL S1 Mini/野火_EBF6ULL S1 Mini 底板_V1.0_原理图.pdf>`
机械尺寸图              :download:`野火_EBF6ULL S1 Mini 底板_V1.0_机械尺寸.pdf <../../hardware/EBF6ULL S1 Mini/野火_EBF6ULL S1 Mini 底板_V1.0_机械尺寸.pdf>`
机械尺寸图（CAD版本）    :download:`野火_EBF6ULL S1 Mini 底板_V1.0_机械尺寸.pdf <../../hardware/EBF6ULL S1 Mini/野火_EBF6ULL S1 Mini 底板_V1.0_机械尺寸.pdf>`
装配图                  :download:`野火_EBF6ULL S1 Mini 底板_V1.0_装配图.pdf <../../hardware/EBF6ULL S1 Mini/野火_EBF6ULL S1 Mini 底板_V1.0_装配图.pdf>`
底板机械尺寸_CAD图.dxf   :download:`野火_EBF6ULL S1 Mini 底板_V1.0_机械尺寸_CAD图.dxf <../../hardware/EBF6ULL S1 Mini/野火_EBF6ULL S1 Mini 底板_V1.0_机械尺寸_CAD图.dxf>`
封装库                  待添加
=====================  ====================

产品概述
------------------------

EBF6ULL S1 Mini开发板是野火电子基于NXP i.MX 6ULL系列处理器设计的一款低功耗单板电脑，
工业级主频最高可达 792MHz，具体如下图。

.. image:: media/imx6mi002.jpeg
   :align: center
   :alt: EBF6ULL S1 Mini开发板


EBF6ULL S1 Mini开发板提供完整的SDK驱动开发包、核心板封装库，底板应用参考设计原理图，
可帮助客户大大缩减产品的开发时间，加快产品上市。目前提供Linux 4.1.15版本的内核，配套的系统自带python、Qt等组件。

开发板整板由EBF6ULL S1核心板模组和底板组成，元件采用工业级选料，
其中核心板板载主控芯片512MB DDR3L内存，256/512MB Nand-FLASH（或8GB eMMC）。

配套的核心板说明见《:doc:`ebf6ulls1`》


EBF6ULL Mini底板硬件资源
------------------------

EBF6ULL Mini底板硬件资源如下。

EBF6ULL S1 Mini开发板硬件资源图（正面）：

.. image:: media/imx6mi005.jpg
   :align: center
   :alt: EBF6ULL S1 Mini开发板硬件资源图（正面）


EBF6ULL S1 Mini开发板硬件资源图（背面）:

.. image:: media/imx6mi006.jpeg
   :align: center
   :alt: EBF6ULL S1 Mini开发板硬件资源图（背面）



EBF6ULL S1 Mini底板参数如下：

===============    =================================================================

PCB                 6层黑色沉金，尺寸为100x61.8mm

100M以太网接口      2路百兆以太网接口

5V电源接口          使用5V±2%单电源供电

过压保护指示灯      该灯亮时表示电压超出范围

USB Device接口     使用Type C接口引出

UART TTL接口       主控器串口引脚直接引出，TTL电平

树莓派接口          包含UART、I2C、SPI、PWM等兼容树莓派的IO接口

心跳灯与电源灯      系统运行后心跳灯会持续闪烁

LCD FPC接口         含24位RGB 接口及I2C触摸屏控制接口

复位&按键           共4个按键，分别为复位、ON/OFF、普通按键及Mode模式切换按键

USB Host Type A     1路使用Type A引出USB Host接口

Boot开关            一个8位拨码开关，支持切换NAND、eMMC、SD及USB启动方式

GPIO扩展口          包含主控器的其它GPIO

RTC电池接口         可接入型号为CR1220的电池为RTC模块供电

SD卡槽              micro SD卡插槽，支持SD卡3.0

IO扩展              包含一个74LV595PW芯片，把某4路IO扩展成8路
===============    =================================================================

