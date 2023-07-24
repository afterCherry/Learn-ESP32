# Wire up the FT2232 with ESP32
![connection](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/connection.png)

# Words
- OpenOCD（Open On-Chip Debugger）: 开源的调试和编程工具，可以连接到嵌入式设备的调试接口（如 JTAG、SWD 等），提供了一系列命令和功能，用于与目标设备通信、读写寄存器、查看内存内容、下载程序等操作。<br>
OpenOCD 支持许多不同的调试接口和芯片，因此可以用于多种不同的嵌入式系统和处理器架构。它被广泛用于开发和调试各种类型的嵌入式设备，包括单片机、微控制器、系统级芯片等。<br>
OpenOCD 是开源软件，所以它的源代码是公开可用的，任何人都可以自由使用、修改和分发。它的开源性质使得开发人员和制造商能够根据自己的需求对其进行定制和扩展，从而更好地满足特定的调试和编程需求。<br>
- so forth 依次类推
- launch the debugger
- FT2232: USB 转串口芯片。FT2232 芯片可以通过 USB 接口连接到计算机，并提供两个串行通信通道（即两个 UART）。它允许计算机通过 USB 接口与外部设备进行串行通信，实现 USB 到串口的转换。<br>
被广泛用于嵌入式系统、开发板和其他需要与计算机进行串口通信的应用中。它提供了高度集成的解决方案，可以方便地将串行设备连接到计算机，无需使用独立的串口硬件。<br>

