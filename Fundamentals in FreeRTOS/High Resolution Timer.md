- FreeRTOS Timer: resolution of only one millisecond
- Callback task: low priority, we should pay attention to non-blocking

```C++
#include "driver/gpio.h"

// set the direction to be output
gpio_set_direction(GPIO_NUM_4, GPIO_MODE_OUTPUT);

const esp_timer_create_args_t esp_timer_create_args = {
    .callback = timer_callback,
    .name = "My timer"};


esp_timer_create(&esp_timer_create_args, &esp_timer_handle);
esp_timer_start_periodic(esp_timer_handle, 50);// 50us to fire this function

if (x++ == 5)
{
    esp_timer_stop(esp_timer_handle);
    esp_timer_delete(esp_timer_handle);// clean up
}
```


# Words
- `esp_timer_dump()` : 打印当前系统时钟的状态信息到调试串口，用于调试和性能分析，帮助开发者了解系统时钟的情况，包括时钟频率、时钟周期等信息。<br>
可以在开发过程中更好地理解程序的时间开销，优化代码以提高性能，并找出哪些部分可能需要更多的注意。<br>


- KHZ kilohertz
- oscilloscope 示波器
- flick 轻弹，闪烁 flick between false and true
- impose 强加
- scroll down
- primer 底漆
- optional 选修的
- dispatch 派遣
