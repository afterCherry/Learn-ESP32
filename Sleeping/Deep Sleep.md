# timer
```C++
#include "esp_sleep.h"

esp_sleep_enable_timer_wakeup(5 * 1000000);

esp_deep_sleep_start();
```

# EXT0
It actually turn on the RTC peripherals while EX1 does not.

```C++
#include "driver/rtc_io.h"

```

# EXT1
- Compared with EXT0, EXT1 gives us more capabilities.
![button](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/button.png) <br>
![interact](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/interact.png) <br>


# Words
- `esp_sleep_pd_config`：配置深度睡眠模式（Deep Sleep Mode）的结构体类型，配置在深度睡眠模式下哪些功耗域将被保持，哪些功耗域将被关闭。`pd` 表示 Power Domain（功耗域）。<br>

定义：<br>

```c
typedef struct {
    uint32_t pd_domain[ESP_PD_DOMAIN_MAX];
} esp_sleep_pd_config_t;
```

结构体中有一个 `pd_domain` 数组，数组的每个元素对应一个功耗域，用于表示该功耗域的配置状态。`ESP_PD_DOMAIN_MAX` 定义了最大的功耗域数目。<br>

`pd_domain` 数组的每个元素可以取以下值：<br>
`ESP_PD_DOMAIN_RTC_PERIPH`：RTC外设功耗域。<br>
`ESP_PD_DOMAIN_RTC_SLOW_MEM`：RTC慢速内存功耗域。<br>
`ESP_PD_DOMAIN_RTC_FAST_MEM`：RTC快速内存功耗域。<br>
`ESP_PD_DOMAIN_XTAL`：外部晶振功耗域。<br>
`ESP_PD_DOMAIN_MAX`：表示数组结束。<br>


