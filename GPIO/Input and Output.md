General Purpose Inputs and Outputs <br>
FET: Field Effect Transistor

# transistor tester
![transistor tester](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/transistor%20tester.png)<br>
![pin1 and 2](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/pin1%20and%202.png)<br>

# For project
Voltage pin on esp32 is 3.3v, the voltage passed the diode is 2.75v, so the voltage between pin1 and pin2 is 3.3-2.75=0.55v <br>
R = V / I <br>
R = 0.55 / 0.02 <br>
R = 30 OHMS <br>

![current through resistor](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/current%20through%20resistor.png) <br>

![circuit diagram](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/circuit%20diagram.png) <br>

Q: What type of FET can I use in order to actually drive a higher load than 20 milliamps through the circuit? <br>
A: We care about the voltage supply and voltage wanted. Vgs=3.3v

![FET](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/FET.png) <br>

![voltage of FET](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/voltage%20of%20FET.png) <br>

![measure volatge of transistor](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/measure%20voltage%20of%20fet%20and%20transistor.png) <br>

![switch circuit](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/switch%20circuit.png) <br>



```C++
// 作用: 将 PIN_LED 引脚的方向设置为输出模式
// PIN_LED: 可能是一个宏或常量，代表所连接的 LED 灯的 GPIO 引脚编号
// gpio_set_level() 函数: 控制 LED 灯的亮灭，将引脚电平设置为高电平（1）或低电平（0）。
gpio_set_direction(PIN_LED, GPIO_MODE_OUTPUT);


// 作用: 将特定的 GPIO 引脚与可编程的输入/输出 "pad" 相关联，这些引脚可用于与外部设备进行数据交换、控制外部器件的状态、读取传感器数据等。
// gpio_pad_select_gpio(PIN_SWITCH);


// 作用: 将 PIN_SWITCH 引脚的方向设置为输入模式
// PIN_SWITCH: 可能是一个宏或常量，代表所连接的开关或传感器的 GPIO 引脚编号
// gpio_get_level() 函数: 读取引脚的电平状态，判断开关是否按下或传感器输出的信号。
gpio_set_direction(PIN_SWITCH, GPIO_MODE_INPUT);

// 作用: 启用了 PIN_SWITCH 引脚的下拉电阻。在输入模式下，如果没有外部信号作用在引脚上，启用下拉电阻将使得引脚被拉低至逻辑低电平（通常为GND），防止未连接或未稳定的输入导致误操作。
gpio_pulldown_en(PIN_SWITCH);
// gpio_pullup_en(PIN_SWITCH);

// 作用: 禁用了 PIN_SWITCH 引脚的上拉电阻。这意味着在输入模式下，引脚将不会被拉高至逻辑高电平（通常为VCC）。这可能是因为在该代码段中，已经启用了下拉电阻，因此禁用上拉电阻。
gpio_pullup_dis(PIN_SWITCH);

```
![pull-up registor](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/pull-up%20registor.png) <br>

![pull-down registor](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/add%20pull-down%20register.png) <br>

# World
- pull-up and pull-down resistor: 用就enable，不用就disable
- 引脚: 每个 GPIO 引脚都可以具有不同的功能，例如作为数字输入、数字输出、模拟输入等
- Pull-up和Pull-down电阻: 控制数字输入引脚电平状态 <br>

1. **Pull-up电阻**：<br>
连接到数字输入引脚和正电源（VCC）之间。当没有外部信号作用在输入引脚上时，Pull-up电阻将使输入引脚被拉高至逻辑高电平（通常为VCC）。<br>
Pull-up电阻的作用是确保在没有外部信号时，输入引脚保持在已知状态。这样可以防止未连接或未稳定的输入导致的误操作。<br>
当外部信号拉低输入引脚时，信号会与Pull-up电阻形成一个电压分压器，使得输入引脚的电压降低，从逻辑高电平转变为逻辑低电平。<br>

2. **Pull-down电阻**：<br>
连接到数字输入引脚和地（GND）之间。当没有外部信号作用在输入引脚上时，Pull-down电阻将使输入引脚被拉低至逻辑低电平（通常为GND）。<br>
Pull-down电阻的作用与Pull-up电阻相似，也是确保在没有外部信号时，输入引脚保持在已知状态。<br>
当外部信号拉高输入引脚时，信号会与Pull-down电阻形成一个电压分压器，使得输入引脚的电压升高，从逻辑低电平转变为逻辑高电平。<br>

综上所述，Pull-up和Pull-down电阻用于在数字输入引脚上建立稳定的逻辑电平，以防止未连接或未稳定的输入导致的误操作。这些电阻在数字电路设计中非常常见，特别是在使用开关或按钮等外部信号输入的情况下。
- Put a delay and the watchdog timer is going to be happy.
- `gpio_get_level(PIN_SWITCH)`: 读取特定GPIO引脚的电平状态， `PIN_SWITCH` 是一个代表GPIO引脚编号的常量或宏。<br>

返回值为整数，通常是 0 或 1。其中，0 表示引脚处于低电平状态（GND），1 表示引脚处于高电平状态（VCC）。<br>

- milliAmps per pin: mA
- exterior world 外部世界
