# SSD Wire up
3V3- 3V3 <br>
GND- GND <br>
CS(Chip Select)- S5(Slave 5) <br>
MOSI- 21 <br>
CLK- 18 <br>
MISO- 19 <br>

![sd card backside](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/sd%20card%20back.png) <br>
![ssd wire](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/ssd%20wire.png) <br>

# SSD Code
```C++
#include <driver/spi_master.h>

#define PIN_CLK 14
#define PIN_MOSI 13
#define PIN_RESET 26
#define PIN_DC 27
#define PIN_CS 15
```

# Wire up Display
- SSD 1306: SPI display screen
![pin mapping](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/pin%20mapping.png) <br>
![display mapping](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/display%20mapping.png) <br>

# Show Display

```C++
u8g2_DrawBox(&u8g2, 10,20, 20, 30);
u8g2_SetFont(&u8g2, u8g2_font_ncenB14_tr);
u8g2_DrawStr(&u8g2, 0,15,"Hello World!");
u8g2_DrawCircle(&u8g2,30, 20, 10,U8G2_DRAW_ALL);
```

![show](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/show.png)


# Words
- slate 石板
- render 渲染，呈现
- `u8g2_esp32_hal.h`: 针对 ESP32 平台的 U8g2 图形库的硬件抽象层（HAL）。U8g2 是一种用于嵌入式系统的图形库，可以用于在 OLED、LCD 和其他显示屏上绘制文本、图形和图像等。<br>

在 ESP32 上使用 U8g2 图形库时，需要提供特定的硬件抽象层，以适配 ESP32 的硬件和底层驱动。硬件抽象层是为了将 U8g2 图形库与特定硬件平台解耦，使其能够在不同的硬件平台上运行而不需要修改核心库。`u8g2_esp32_hal.h` 文件中定义了一些函数和接口，用于与 ESP32 的硬件进行交互，比如初始化硬件、设置引脚、SPI 和 I2C 通信等。<br>
- 32bits 10bucks: 32 位处理器的硬件或产品，其价格为 10 美元。
- SPI（Serial Peripheral Interface）: 一种用于串行数据通信的同步通信协议和接口标准。
SPI 使用主从结构，其中一个设备充当主设备（Master），控制通信的时序和传输，而其他设备则充当从设备（Slave）。通信过程中，主设备负责生成时钟信号，并通过多条数据线同时传输数据和接收数据。

4 data lines <br>
Each device on the bus require an additional GPIO pin <br>
Faster than I2C <br>
MOSI- Master Out, Slave In <br>
SS- Slave Select <br>

![2 devices](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/two%20devices.png)



