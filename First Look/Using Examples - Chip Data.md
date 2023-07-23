# Features Steps
1. ESP-IDF —> Examples —> Get Started —> Hello World
2. Copy the directory to where you set up for a first-look position
3. Go into the directory "Hello World", right click to choose "Open with code"
4. Go to C file(hello_world_main.c), which appears lacking of dependencies <br>
![lack of dependencies](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/lack%20of%20dependency.png) <br>
5. Copy directory ".vscode" to the same position as "Hello World"

```C++
esp_chip_info_t:type

unassigned: can't be negtive >=0

32: 32bit, also 4 bytes

features: does it have Wi-Fi, Flash, Bluetooth, Bluetooth Low Energy?

fflush(stdout): Data was stored in the buffer before, and not flushed to the output. Here force data in buffer to get flushed.

esp_get_idf_version

mac address: uniquely identify what esp-chip is

```
![features](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/features.png) <br>
Reparse to stop compiling. <br>

idf_version & mac address:
```C++
printf("idf version is %s\n", esp_get_idf_version());

uint8_t chipId[6];
esp_efuse_mac_get_default(chipId);
printf("mac / chip id: %02x%02x%02x%02x%02x%02x\n", chipId[0], chipId[1], chipId[2], chipId[3], chipId[4], chipId[5]);
```
![esp chip mac address](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/chip%20id%20mac%20address.png)

# Words
- hexadecimal 16进制
- MAC（Media Access Control） address: serial number. MAC地址是网络设备（如计算机、手机、路由器等）在物理层（数据链路层）上的唯一标识符。它由48位二进制数字组成，通常表示为12个十六进制数，用冒号或连字符分隔，例如：00:1A:2B:3C:4D:5E。<br>

每个网络设备都有一个独特的MAC地址，它用于在局域网中识别和寻址设备。当数据从一个设备发送到另一个设备时，会使用目标设备的MAC地址来确定数据的传输路径，以确保数据被正确传送到目标设备。<br>

在网络通信中，数据包通常在发送过程中会被封装在一个帧中，该帧包含源设备和目标设备的MAC地址。当数据包到达目标设备时，设备会检查帧中的目标MAC地址与自身的MAC地址是否匹配，如果匹配则接收数据包，否则将丢弃该数据包。<br>
- flush 冲水
- WROOM: 通常指的是“ESP-WROOM”模块，是一种由Espressif Systems开发的Wi-Fi模块。它基于ESP8266芯片，并集成了Wi-Fi和处理器等功能，方便用户在嵌入式系统中实现无线网络连接。<br>

ESP-WROOM模块具有以下特点：<br>
1. Wi-Fi功能：支持802.11 b/g/n标准，可实现可靠的无线网络连接。<br>
2. 处理器：集成了ESP8266芯片，该芯片包含一个32位的Tensilica L106 RISC处理器，可运行应用程序和处理网络通信。<br>
3. 存储：拥有内置的Flash存储器，可存储应用程序和数据。<br>
4. 低功耗：具有优秀的低功耗特性，适合在电池供电的嵌入式系统中使用。<br>
5. 丰富的接口：支持多种通信接口，如SPI、UART、I2C等，便于与其他设备进行通信和连接。<br>

由于ESP-WROOM模块具有简单、成本低廉和易于集成的特点，因此在物联网（IoT）和嵌入式系统中得到广泛应用。它为开发者提供了一种简便的方式来实现Wi-Fi连接，使得开发无线网络应用变得更加便捷。
- /(1024*1024): bytes —> megabytes
- esp_chip_info(address): Take the thing, put it here, and fill it up. Once it's filled, we can read it.
- F12：查看源码
- SPI(Serial Peripheral Interface):串行外设接口协议，用于在微控制器和其他外部设备之间进行通信。SPI常用于连接微控制器、传感器、存储器、显示屏等各种外设。<br>

SPI使用4根信号线进行通信：<br>
1. SCLK（Serial Clock）：时钟信号，由主设备产生，用于同步数据传输。<br>
2. MOSI（Master Out Slave In）：主设备发送数据给从设备的信号线。<br>
3. MISO（Master In Slave Out）：从设备发送数据给主设备的信号线。<br>
4. SS/CS（Slave Select/Chip Select）：从设备的片选信号线，用于选择与主设备通信的从设备。<br>

SPI的特点包括：
串行通信：数据在一位一位地传输，减少了引脚的数量，使得通信线路更简单。<br>
全双工通信：主设备和从设备可以同时发送和接收数据。<br>
高速传输：由于采用串行通信，SPI可以在较高的速率下进行数据传输。<br>
- "esp_spi_flash.h": information about the flash(memory)
- "esp_system.h": information about the chip
- time out 暂停
- dependency 依靠—>环境依赖
- diagnostic 诊断的
