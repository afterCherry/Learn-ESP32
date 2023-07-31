The ESP32 can also be a station.
![internet connection](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/internet%20connection.png)

# CMakeLists.txt
```C++
set(EXTRA_COMPONENT_DIRS $ENV{IDF_PATH}/examples/common_components/protocol_examples_common)
include($ENV{IDF_PATH}/tools/cmake/project.cmake)
```
![connect examples](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/connect%20examples.png) <br>

# main.c
```C++
#include "esp_wifi.h"
#include "esp_event.h"
#include "protocol_examples_common.h"
```
![connect ip address](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/connect%20ip%20address.png) <br>


# Words
- `nvs_flash_init()` ：初始化 Non-Volatile Storage (NVS) 。NVS 用于在芯片的非易失性存储器中保存应用程序的配置和状态信息。在使用 NVS 之前，需要调用 `nvs_flash_init()` 函数进行初始化，以便在芯片上正确配置 NVS。
- `esp_netif_init()` ：初始化 ESP32 网络接口。在使用网络功能之前，需要调用 `esp_netif_init()` 函数进行初始化，以便正确配置网络接口和协议栈，包括 Wi-Fi 和以太网功能等。
