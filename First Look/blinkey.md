# pin
- Codes for microcontroller
- No built-in LED: Just add LED to one of the pins with a resistor between 100ohms and 300ohms

```C++
#include "driver/gpio.h"

#define PIN 2

```

The flip is so fast that we even don't notice it switch on and switch off, so we put a delay here. <br>
![pin_delay](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/pin_delay.png) <br>
The implement effect is as we expected. <br>
![on](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/on.png) <br>
![off](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/off.png) <br>



# Words
- gpio_set_level() : 一个函数，用于设置GPIO引脚的电平状态。GPIO（General Purpose Input/Output）引脚是用于与外部电路进行数字通信和控制的通用引脚。
接受两个参数：引脚编号和电平状态。引脚编号指定要设置电平状态的GPIO引脚，而电平状态则指定要设置的电平，通常为高电平（1）或低电平（0）。
- cast 投掷
- flip 翻转
- VS Code 的自动补全无敌
- f12: go to definition
- autostropriatos 自动旋转
- blinkey 眨眼😉
