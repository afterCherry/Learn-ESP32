Log works like `printf`. <br>

# main.c
```C++
#include<stdio.h>
#include "esp_log.h"

void app_main(void){
  ESP_LOGE("LOG","This is an error");
}
```
- ESP_LOGE: log error 

```C++
idf.py flash monitor
```

Reparse the ESP32 again. Close and open the VS Code, then the problem should go away. <br>
![esp32](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/click%20esp32.png) <br>
![choose esp32](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/choose%20esp32%20to%20reparse.png) <br>

```C++
#include<stdio.h>
#include "esp_log.h"

void app_main(void){
  ESP_LOGW("LOG","This is a warning.");
  ESP_LOGI("LOG","This is an information.");
  ESP_LOGD("LOG","This is a Debug Statement.");
  ESP_LOGV("LOG","This is Verbose.");
}
```
- ESP_LOGW: log warning
- ESP_LOGI: log information
- ESP_LOGD: log debug statement, default to be turned off
- ESP_LOGV: log verbosely, default to be turned off

The number tells you the milliseconds after the application started. <br>
![log](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/log.png) <br>


Open ESP-IDF Command Prompt and use Menuconfig to open ESP_LOGD and ESP_LOGV <br>

```C++
idf.py menuconfig
```
![idf command prompt](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/idf%20command%20prompt.png) <br>
![component config](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/component%20config.png) <br>
![log output](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/log%20output.png) <br>
![default](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/default.png) <br>
![debug and verbose](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/debug%20and%20verbose.png) <br>
![counter number](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/count%20number.png) <br>

```C++
#include<stdio.h>
#include "esp_log.h"

void app_main(void){
  esp_log_level_set("LOG", ESP_LOG_INFO);
  ESP_LOGE("LOG","This is an error");
  ESP_LOGW("LOG","This is a warning.");
  ESP_LOGI("LOG","This is an information.");
  ESP_LOGD("LOG","This is a Debug Statement.");
  ESP_LOGV("LOG","This is Verbose.");

  ESP_LOGE("TAG 2","This is an error");
  ESP_LOGW("TAG 2","This is a warning.");
  ESP_LOGI("TAG 2","This is an information.");
  ESP_LOGD("TAG 2","This is a Debug Statement.");
  ESP_LOGV("TAG 2","This is Verbose."); 
}
```

# Words
- verbose logging 详细记录
- tie up 捆绑
- tag 标签
- utilize 利用
- blink 眨眼
