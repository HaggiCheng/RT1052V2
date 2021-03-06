# RT1052V2

**SphinxEVK**是由SphinxEVK项目成员[StackYuan](https://github.com/StackYuan)设计的，基于I.MXRT1052系列MCU的核心板。板上关键信号(SDRAM, nor flash, sd card)均设计了等长，使用了4-layer，4mil/4mil(线宽/线间距)，直径8mil/14mil(孔/带焊环)的生产工艺，可以被当前主流PCB打样厂生产。

注: 

> 开发板设计了严格的上电时序和电源域，同时兼容RT1052 A0和A1版本。
> 
> 为了减小体积，开发板使用78mil/2.00mm排针设计。如调试飞线感到不便，工程下也提供了标准100mil/2.54mm的IO拓展板：**SphinxEVK_ExtIO.PcbDoc**。

---

**板上资源：**

> 1.预留QSPI nor flash/Hyperflash双焊盘
> 
> 2.预留SDRAM焊盘
> 
> 3.RGB565 CSI接口(异面兼容[龙邱MT9V034](https://item.taobao.com/item.htm?spm=a1z10.1-c-s.w5003-17544280197.3.4d1e5e05JhMYK8&id=562070292609&scene=taobao_shop))
> 
> 4.RGB565 DSI接口
> 
> 5.KSZ8081 ENET PHY
> 
> 6.引出Micro USB(**USB1**) 
> 
> 7.引出UART(**LPUART1**)
> 
> 8.引出SWD(带RST)
> 
> 9.引出SDIO(TF slot)
> 
> 10.引出所有非关键IO

---
**勘误：**

> 1.使用LQ神眼摄像头时，由于IIC线序错误，故使用软件IIC进行初始化
> 
> 2.SD卡可能会出现枚举失败问题，原因是进入高速模式时，主芯片NVCC_SDIO脚不能完成3.3V->1.8V电压的切换。建议暂使用低速模式。
> 
> 3.UART1 RXD未设置上拉，可能在进行ISP模式时由于RT的内部bootloader检测失误，造成USB下载模式不能进入。
> 
---
**SphinxEVK实物图**

![image](https://github.com/SphinxEVK/RT1052V2/blob/master/SphinxEVK.jpg)
