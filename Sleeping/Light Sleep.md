# Timer
```C++
#include <time.h>
#include "esp_sleep.h"
#include "esp_timer.h"


// unit-us(microseconds)
esp_sleep_enable_timer_wakeup(5000000);

```

# GPIO
wake up with a button click using the GPIO.

```C++
#include "driver/rtc_io.h"

```


# Words
- ternary 三元符
- entail 蕴含
- stall 摊位，停滞
- `esp32/rom/uart.h`: 提供了一些与 UART（Universal Asynchronous Receiver/Transmitter）串口通信相关的功能。`rom` 表示该头文件中的函数和数据是存储在芯片的只读存储器（ROM）中，这些函数通常是硬件相关且高度优化过的。由于存储在ROM中，因此这些函数的功能是固定的，无法修改。以下是该头文件中一些常见的功能：<br>
1. **UART初始化：** 使用 `uart_rx_enable()` 和 `uart_tx_enable()` 函数可以初始化 UART 接收和发送功能。<br>
2. **UART发送数据：** 使用 `uart_tx_one_char()` 函数可以向 UART 发送一个字节的数据。<br>
3. **UART接收数据：** 使用 `uart_rx_one_char()` 函数可以从 UART 接收一个字节的数据。<br>
4. **UART中断配置：** 使用 `uart_intr_enable()` 函数可以配置 UART 的中断，以便在接收数据时触发中断处理。<br>
5. **波特率设置：** 使用 `uart_div_modify()` 函数可以设置 UART 的波特率。<br>
6. **FIFO缓冲区：** 该头文件中还包含了 FIFO 缓冲区相关的函数和宏定义，用于管理 UART 的接收和发送缓冲区。<br>

需要注意的是，`esp32/rom/uart.h` 中的函数都是在芯片的ROM中存储的，因此它们不需要通过链接器进行链接，可以直接调用。
- `esp_sleep.h`: 提供了一些与睡眠模式（Sleep Mode）相关的功能：<br>
1. **进入睡眠模式：** 使用 `esp_sleep_enable_XXX_mode()` 函数可以配置芯片进入特定类型的睡眠模式，例如深度睡眠（Deep Sleep）模式或Light Sleep模式。<br>
2. **睡眠延时：** 使用 `esp_deep_sleep()` 函数可以使芯片进入深度睡眠模式，并设置睡眠延时，让芯片在一段时间后自动唤醒。<br>
3. **唤醒原因：** 使用 `esp_sleep_get_wakeup_cause()` 函数可以获取芯片的唤醒原因，即芯片进入睡眠模式后是由什么事件或信号唤醒的。<br>
4. **RTC唤醒定时器：** 可以使用 `esp_sleep_enable_timer_wakeup()` 函数配置RTC（Real-Time Clock）唤醒定时器，让芯片在指定的时间后唤醒。<br>
5. **外部中断唤醒：** 可以使用 `esp_sleep_enable_ext0_wakeup()` 和 `esp_sleep_enable_ext1_wakeup()` 函数配置外部中断唤醒，让芯片在外部事件触发时唤醒。<br>
6. **Touch唤醒：** 可以使用 `esp_sleep_enable_touchpad_wakeup()` 函数配置Touch唤醒，让芯片在Touch触发时唤醒。<br>
7. **Ultra Low Power协处理器：** ESP32芯片支持Ultra Low Power（ULP）协处理器，可以使用 `esp_sleep_enable_ulp_wakeup()` 函数配置ULP唤醒。<br>
- `time.h`: 提供了一些与时间和日期相关的功能。<br>
1. **获取当前时间：** 使用 `time()` 函数可以获取当前的系统时间，返回从1970年1月1日开始经过的秒数（时间戳）。<br>
2. **时间结构：** 使用 `struct tm` 结构体来表示时间，它包含了年、月、日、时、分、秒等字段，方便对时间进行操作和处理。<br>
3. **时间格式化：** 使用 `strftime()` 函数可以将时间格式化为指定的字符串格式，方便输出或显示。<br>
4. **时间解析：** 使用 `strptime()` 函数可以将字符串形式的时间解析为 `struct tm` 结构体，方便处理用户输入的时间。<br>
5. **时间运算：** 可以使用 `difftime()` 函数计算两个时间之间的时间差，或者使用 `mktime()` 函数将 `struct tm` 结构体转换为时间戳。<br>
6. **休眠：** 使用 `sleep()` 函数可以使程序暂停执行一段指定的时间。<br>
7. **定时器：** 可以使用 `clock()` 函数来实现简单的定时器功能，测量程序的运行时间。<br>
8. **获取日期和时间信息：** 可以使用 `gmtime()` 函数获取当前的世界标准时间（GMT）的 `struct tm` 结构体，或使用 `localtime()` 函数获取当前系统的本地时间的 `struct tm` 结构体。<br>
