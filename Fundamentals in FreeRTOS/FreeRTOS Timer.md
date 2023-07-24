```C++
#include "esp_timer.h"

// the name of timer; the amount of time; whether we want this to repeat or to reload;
// ID; call back that should happen once the actual timer is reached
TimerHandle_t xTimer = xTimerCreate("my timer", pdMS_TO_TICKS(1000), true, NULL, on_timer);

// parameter2: how long do you want to wait before the timer get kicked off
xTimerStart(xTimer, 0);

```

- 1s == 1000ms

# Words
- turn over 翻动
- elapse 过去
- kick off 开始
- `esp_timer_get_time()` :  ESP-IDF（ESP32 IoT Development Framework）中提供的函数，获取当前系统时钟的时间，单位为微秒（us microsecond）<br>
esp_timer_get_time() / 1000 单位转化为毫秒


