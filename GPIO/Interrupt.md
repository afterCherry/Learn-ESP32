


```C++
// 初始化 GPIO 中断服务
//  0: 设置为默认的中断分配器
gpio_install_isr_service(0);

// PIN_SWITCH: 代表 GPIO 引脚编号的常量或宏，它指定要配置的 GPIO 引脚。
// gpio_isr_handler: 中断处理函数的名称，它是一个用户定义的函数，当 PIN_SWITCH 引脚上的中断被触发时，这个函数将被调用来处理中断事件。
// (void *)PIN_SWITCH: 用户提供的参数，用于传递给中断处理函数的参数。在这里，它被设置为 PIN_SWITCH 的值，以便在中断处理函数中可以获取到触发中断的引脚编号。

gpio_isr_handler_add(PIN_SWITCH, gpio_isr_handler, (void *)PIN_SWITCH);
```
![interact between hardware and software](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/interact%20between%20hardware%20and%20software.png)

# Words
- `xQueueSendFromISR()`: 在中断服务例程中向 FreeRTOS 队列发送数据。它会立即将数据放入队列，而不会阻塞中断服务例程的执行。随后，你可以在任务（非中断上下文）中使用 `xQueueReceive()` 等函数来接收并处理队列中的数据。这样可以实现中断和任务之间的通信，而不会引起优先级问题或竞争条件。<br>

函数参数解释如下：<br>
`interruptQueue`：这是一个指向目标队列的指针，即你希望将数据发送到的队列。<br>
`&pinNumber`：这是要发送的数据的指针。在这个例子中，`pinNumber` 是一个变量，其中包含要发送的数据（比如 GPIO 引脚号）。<br>
`NULL`：这是一个指向返回值的指针。在 `xQueueSendFromISR()` 中，我们通常将其设置为 `NULL`，因为我们不需要获取队列操作的返回值。<br>
- `gpio_set_intr_type(PIN_SWITCH, GPIO_INTR_POSEDGE)`: 在 ESP32 或 ESP8266 微控制器上，每个 GPIO 引脚都可以配置为中断触发源，当引脚上的电平发生变化时，可以触发一个中断。中断触发类型可以配置为上升沿触发、下降沿触发、任何边沿触发或禁用中断。<br>
在使用中断之前，你需要首先配置引脚的功能为普通的数字输入功能（通常通过 gpio_pad_select_gpio() 函数），然后再配置中断触发类型。
![switch posedge](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/switch%20posedge.png) <br>

