# Basic Echo
- pin4(TX) and pin5(RX) were connected together.
![connect pins](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/connect%20pins.png) <br>


```C++
#include "driver/uart.h"

#define TXD_PIN 4
#define RXD_PIN 5

uart_config_t uart_config = {
  .baud_rate = 9600,
  .data_bits = UART_DATA_8_BITS,
  .parity = UART_PARITY_DISABLE,
  .stop_bits = UART_STOP_BITS_1,
  .flow_ctrl = UART_HW_FLOWCTRL_DISABLE
};

// 将参数 `uart_config` 应用于该 UART 端口的配置
uart_param_config(UART_NUM_1 ,&uart_config);
```
![ping successful](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/ping%20successful.png)

# UART to PC Communication
![bluetooth pin](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/bluetooth%20pin.png) <br>

![esp32 pin](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/esp32%20pins.png) <br>

![bluetooth connection](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/bluetooth%20connection.png) <br>

default pin for JDY-31 is "1234" <br>

![PC Computer Connection](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/PC%20Computer%20bluetooth.png) <br>
![port](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/port.png) <br>

The receiving info is limited to speed.<br>
![receive info](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/receive%20info.png)<br>
![limited to speed](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/limited%20to%20speed.png)<br>

# Queue
![interrpt](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/interrupt.png)


# Words
- `uart_enable_pattern_det_baud_intr()`: 在 UART（通用异步收发传输）通信中启用模式检测和波特率中断功能。<br>

函数参数解释如下：<br>
`UART_NUM_1`：表示 UART 端口号的参数，用于指定要启用模式检测和波特率中断功能的 UART 端口。<br>
`'+'`：这是一个表示待检测的模式的参数。在此处，`'+'` 表示要检测的模式是一个 '+ ' 字符。也就是说，当接收到一个 '+ ' 字符时，将会触发中断。<br>
`PATTERN_LEN`：这是一个表示模式的长度的参数，用于指定待检测模式的长度。在此处，`PATTERN_LEN` 表示待检测模式的长度为多少个字符。例如，如果设置为 2，那么待检测的模式就是 '+ '。<br>
`10000`：这是一个表示波特率中断时间的参数，用于指定当没有接收到待检测模式的一部分时，多久会触发波特率中断。在此处，设置为 10000 表示当连续 10000 个时钟周期没有接收到 '+ ' 模式的一部分时，会触发波特率中断。<br>
`10`：这是一个表示模式检测中断阈值的参数，用于指定当接收到的模式匹配次数超过这个阈值时，会触发模式检测中断。在此处，设置为 10 表示当接收到的连续模式匹配次数达到 10 次时，会触发模式检测中断。<br>
`10`：这是一个表示模式检测中断间隔的参数，用于指定模式检测中断之间的最小时间间隔。在此处，设置为 10 表示两次模式检测中断之间的时间间隔至少为 10 个时钟周期。<br>
- JDY-31 蓝牙模块: 与其他蓝牙设备进行通信，并在电池供电的设备中实现低能耗的无线连接。<br>

JDY-31 蓝牙模块的主要特点包括：<br>
1. **蓝牙低功耗**：JDY-31 使用 BLE 技术，因此在通信过程中消耗较少的能量，非常适合用于电池供电的设备。<br>
2. **简单易用**：JDY-31 提供简单的串口通信接口，可以通过串口通信与其他设备进行数据交换，使用方便。<br>
3. **广泛应用**：由于其低功耗和便捷性，JDY-31 蓝牙模块在物联网、智能家居、传感器网络、健康医疗设备等领域得到广泛应用。<br>
4. **可定制性**：JDY-31 提供了丰富的 AT 指令集，可以通过 AT 指令对模块进行配置和控制，满足不同应用场景的需求。<br>
- `uart_driver_install(UART_NUM_1, RX_BUF_SIZE, 0, 0, NULL, 0)`: 安装 UART 驱动程序的函数调用，用于初始化并启动指定 UART 端口的驱动程序，以便在应用程序中进行串口通信。<br>

函数参数解释如下：<br>
`UART_NUM_1`：指定要安装驱动程序的 UART 端口。<br>
`RX_BUF_SIZE`：指定接收数据时的缓冲区大小。接收缓冲区是用于存储从串口接收到的数据的内存区域。<br>
`0`：这是一个表示发送缓冲区大小的参数，用于指定发送数据时的缓冲区大小。在此处设置为 0 表示不使用发送缓冲区，即不缓冲发送的数据，而是直接发送。<br>
`0`：这是一个表示 UART 队列长度的参数，用于指定 UART 队列中可以存储的数据项数量。在此处设置为 0 表示不使用队列，即接收数据不会被存储在队列中，而是直接存储在接收缓冲区中。<br>
`NULL`：这是一个表示 UART 队列句柄的参数，用于指定一个用于存储接收数据的队列句柄。在此处设置为 NULL 表示不使用队列，即接收数据不会被存储在队列中。<br>
`0`：这是一个表示任务优先级的参数，用于指定 UART 驱动程序任务的优先级。在此处设置为 0 表示使用默认优先级。<br>
- `UART_NUM_1`: 表示 UART 端口号的参数，用于指定要配置的 UART 端口。<br>

ESP32 上内置了多个 UART 端口，常见的 UART 端口标识符有：<br>
`UART_NUM_0`：表示 UART0 端口。<br>
`UART_NUM_1`：表示 UART1 端口。<br>
`UART_NUM_2`：表示 UART2 端口。<br>

需要注意的是，在使用 UART 功能之前，通常需要进行 UART 端口的初始化和配置。配置包括设置波特率、数据位、奇偶校验、停止位等参数，以及设置 UART 的硬件流控制等。只有正确配置 UART 才能实现稳定的串口通信。
- `parity`（奇偶校验）:增加数据传输可靠性的机制。<br>

奇偶校验是一种简单的错误检测方法，用于检测数据传输过程中的位错误。在 UART 通信中，每个数据帧通常包含数据位、起始位和停止位。奇偶校验位是一个附加的位，可以是奇校验位或偶校验位。<br>

具体解释参数中的 `parity`：<br>
- `UART_PARITY_DISABLE`：这表示禁用奇偶校验，数据传输过程中不增加校验位。<br>
- `UART_PARITY_ODD`：这表示使用奇校验。奇校验位会使数据帧中的位数保持奇数，以确保每个数据帧中的 1 位的数量是奇数。发送端会根据数据位的值自动添加或删除校验位，以保证数据帧中 1 的位数为奇数。如果接收端期望奇校验，但收到的数据帧中 1 的位数不是奇数，那么接收端会发现校验错误。<br>
- `UART_PARITY_EVEN`：这表示使用偶校验。偶校验位会使数据帧中的位数保持偶数，以确保每个数据帧中的 1 位的数量是偶数。发送端会根据数据位的值自动添加或删除校验位，以保证数据帧中 1 的位数为偶数。如果接收端期望偶校验，但收到的数据帧中 1 的位数不是偶数，也会发现校验错误。
<br>

在通信过程中，发送端和接收端必须使用相同的奇偶校验设置，以确保数据传输的正确性。如果在通信双方之间约定使用奇偶校验，并且正确地配置了 UART 参数中的 `parity`，则可以提高通信的可靠性和容错性。<br>
- UART（Universal Asynchronous Receiver-Transmitter）: 异步收发传输。一种通信协议和硬件接口，用于在计算机和外部设备之间进行串行数据传输。<br>

UART 是一种异步通信协议，这意味着发送和接收数据时，不需要共享时钟信号。它使用两条信号线：一条用于发送数据（TX，Transmit）和一条用于接收数据（RX，Receive）。通过这两条线，UART 可以实现双向的串行数据传输。<br>

UART 在不同的设备和通信场景中被广泛应用，例如：<br>
1. **计算机串口通信**：过去，许多计算机都配备了串口接口，用于与外部设备（如调制解调器、打印机、外部传感器等）进行通信。<br>
2. **嵌入式系统通信**：许多嵌入式系统使用 UART 与其他外设进行通信，例如与传感器、显示屏、无线模块等进行数据交换。<br>
3. **调试和通信**：UART 通常用于嵌入式系统的调试和日志输出，方便开发者调试程序或查看系统状态。<br>
4. **物联网设备**：在物联网设备中，UART 也常用于与传感器或其他设备进行通信，传输数据或控制指令。<br>

UART 的速率可以灵活设置，通常用波特率（Baud Rate）来表示，表示每秒传输的比特数。常见的波特率有 9600、115200 等，具体的波特率需要在发送和接收设备之间进行协商，保证通信的可靠性。
