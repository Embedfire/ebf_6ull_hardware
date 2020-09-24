
.. vim: syntax=rst


EBF6ULL 开发板引脚分配说明
==========================================

为方便用户使用野火核心板进行二次开发，我们把野火开发板使用到的引脚已整理至资料excel表及i.MX Pins tool中。

- :download:`野火_EBF6ULL S1邮票孔核心板_V1.0引脚分配.xlsx <../../hardware/野火_EBF6ULL S1邮票孔核心板_V1.0引脚分配.xlsx>`
- :download:`野火_EBF6ULL开发板Pin Tool引脚分配文件 EBF6ULL.mex <../../hardware/EBF6ULL_PIN_TOOL/EBF6ULL.mex>`

其中excel表直接用excel打开查看即可，深度设计建议使用i.MX Pins tool工具配合 ``引脚配置文件EBF6ULL.mex`` 进行查看与调节。

i.MX Pins tool简介
------------------------

i.MX Pins tool 是用于i.MX系列处理器的一套引脚配置工具。
它可以使用图形用户界面分配i.MX系列芯片的所有引脚，从复用（复用）到引脚的电气特性，然后生成普通的C代码，然后可以在应用程序中使用。

设计硬件时可以利用它检查硬件复用，非常方便。

软件下载地址：https://www.nxp.com/design/designs/pins-tool-for-i-mx-application-processors:PINS-TOOL-IMX?tab=Design_Tools_Tab

野火_EBF6ULL开发板Pin Tool引脚分配文件
---------------------------------------------

1. 下载上述软件并安装好后，打开软件并加载 ``EBF6ULL.mex`` 文件导入野火引脚配置，如下图：

    .. image:: media/pin_load_config.png
        :align: center
        :alt: 加载配置

#. 加载后，可看到根据野火配置文件生成的一个配置主界面如下图，我们主要使用的是选择功能组、配置功能组属性、选择引脚、
   查看冲突等功能，其中自动生成的源码会根据引脚功能配置自动调整，但我们的配置文件没有配置引脚具体的上下拉、输入输出等属性，
   所以千万不要直接使用生成的源码。

    .. image:: media/pin_main_win.png
        :align: center
        :alt: 主窗口



#. 点击 ``配置功能组属性`` 按钮，可以修改功能组的名称、设置是否勾选 ``在默认初始化函数中调用`` 的选项，

    - 选项 ``在默认初始化函数中调用`` 非常重要，只有勾上该选项，该功能组使用到的引脚才会加入到冲突检测，
      若不勾选，即使检测到有引脚冲突也不会有任何提示。

    - 野火配置文件中，默认已经创建了很多功能组，这些功能组根据野火开发板划分成了核心板、Mini底板、Pro底板、
      其它常用功能以及测试功能组。

    .. image:: media/pin_init_config.png
        :align: center
        :alt: 初始化配置

    .. image:: media/pin_add_test.png
        :align: center
        :alt: 添加测试 配置

#. 野火配置文件中默认功能组命名符合如下规则，方便大家在检查冲突时进行选择。
   命名规则如下：
    - core_xxx ：core 表示野火EBF_6ULL ``核心板`` 硬件外设使用的引脚功能组xxx，其中的xxx主要是两种FLASH：eMMC、NAND、及内存DDR，
      其中eMMC和NAND在核心板里只会同时使用其中一种，它们使用的引脚也有大部分是重合的，此处为了方便，
      配置文件把这两个功能组都默认勾选初始化了，大家可以根据自己实际使用的核心版版本取消其中一个勾选。
      另外，邮票孔、金手指、BTB版本的核心板只是封装不同，使用的引脚分配是完全一样的。

    - mini_xxx ：mini 表示野火EBF_6ULL ``Mini`` 底板上硬件外设使用的引脚功能组xxx，如串口uart1、以太网enet等。

    - mini_xxx_r_yyy ：功能组命名中带了字符 ``r``，它表示这个xxx外设依赖yyy外设使用的引脚，即使用xxx设备前要使能yyy设备。
      如 mini_enet1_r_enet 和 mini_enet2_r_enet 表示网口1和网口2都依赖前面名称为mini_enet_mdc的功能组，
      这两个网口的PHY芯片都需要mdc总线去控制通讯。

    - pro_xxx ：pro表示野火EBF_6ULL ``pro`` 底板上硬件外设使用的引脚功能组xxx，如pro_flexcan1表示can1外设，
      特别地，Pro底板具有Mini底板的所有功能，所以前面介绍的Mini底板功能组在Pro底板是完全适用的。

    - pro_xxx_r_yyy ：与前面类似，功能组命名中带了字符 ``r``，它表示这个xxx外设依赖yyy外设使用的引脚，
      如pro_mpu6050_r_i2c1，表示mpu6050模组依赖前面i2c1功能组的引脚，因为开发板上mpu6050是使用i2c1总线进行通讯的。

    - extra_xxx ：extra表示野火EBF6ULL没有默认使用的功能组，但用核心板做二次开发时又非常常用的功能，如spi1...spi4,uart1...uart8等。

    - test_xxx : 这是我们自己常用的想添加某些功能时使用的功能组，有需要的话你也可以添加自己的功能组进行测试。

由于开发板是做验证功能用，所以有不少功能组在Pro底板是有引脚冲突的，不过开发板在软件控制时只使能了冲突时的其中一个，这样才能正常使用，
做产品开发时建议从硬件上就完全避开冲突。

.. attention:: 经实际使用，有时一些功能外设与GPIO即使使用了同样的引脚，软件也不会提示有冲突，
   但配置了引脚的上下拉、输入输出等才会提示，所以也不能完全信任该冲突检测。