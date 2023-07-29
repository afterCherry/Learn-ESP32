Fast timers generally work on hardware, slow timers generally work on software.<br>
We use different channels to choose different timers that are driving different pins. <br>
![ldec structures](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/ldec%20structures.png) <br>

Refer to the source code to determine how to write the code.<br>
![reference](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/reference.png) <br>



```C++
ledc_timer_config_t timer = {
    .speed_mode = LEDC_LOW_SPEED_MODE,
    .duty_resolution = LEDC_TIMER_10_BIT,
    .timer_num = LEDC_TIMER_0,
    .freq_hz = 5000,
    .clk_cfg = LEDC_AUTO_CLK};

ledc_channel_config_t channel = {
    .gpio_num = 4,
    .speed_mode = LEDC_LOW_SPEED_MODE,
    .channel = LEDC_CHANNEL_0,
    .timer_sel = LEDC_TIMER_0,
    .duty = 0,
    .hpoint = 0};
```
The output is for pin4.<br>
![pin4](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/output%20of%20pin4.png) <br>

duty=0: plain <br>
![duty0](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/duty%3D0.png) <br>

duty=1: short spikes <br>
![duty1](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/duty%3D1.png) <br>

duty=1023: 10bit binary <br>
![duty1023](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/duty%3D1023.png) <br>

duty=1024: full high <br>
![duty1024](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/duty%3D1024.png) <br>

speed mode: gradually pick up and go along <br>
![gradual1](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/gradual%201.png) <br>
![gradual2](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/gradual%202.png) <br>




# Words
- `ledc_set_fade_time_and_start()`: ESP-IDF（Espressif IoT Development Framework）中用于设置 LED 控制器渐变时间并启动渐变过程的函数。<br>

在 ESP32 上，LED 控制器（LEDC）模块允许你对 LED 灯进行精确控制，包括调整 LED 的亮度、频率和占空比等参数。<br>

函数参数解释如下：。<br>
`LEDC_LOW_SPEED_MODE`：这是一个表示 LED 控制器的速度模式的参数。在 ESP32 上，LED 控制器支持两种速度模式：<br>
`LEDC_LOW_SPEED_MODE` 和 `LEDC_HIGH_SPEED_MODE`。<br>

`LEDC_CHANNEL_0`：这是一个表示 LED 控制器通道的参数。在 ESP32 上，LED 控制器支持多个通道，每个通道可以独立控制一个 LED 灯或其他输出设备。`LEDC_CHANNEL_0` 表示选择通道 0。<br>

`0`：这是一个表示渐变起始亮度的参数。在这里设置为 0，表示渐变的起始亮度为 0。<br>

`1000`：这是一个表示渐变结束亮度的参数。在这里设置为 1000，表示渐变的结束亮度为 1000。注意，在 LED 控制器中，通常使用 0 到 1000 的范围来表示亮度变化，其中 0 表示灭，1000 表示最大亮度。<br>

`LEDC_FADE_WAIT_DONE`：这是一个表示渐变模式的参数。`LEDC_FADE_WAIT_DONE` 表示在执行渐变过程时，阻塞代码，直到渐变完成。这意味着在渐变过程中，代码会一直等待，直到渐变完成后再继续执行。<br>

通过调用 `ledc_set_fade_time_and_start()` 函数，你可以设置 LED 渐变的起始亮度和结束亮度，并启动 LED 的渐变过程。在渐变过程中，LED 会从起始亮度平滑地过渡到结束亮度。如果设置了 `LEDC_FADE_WAIT_DONE` 参数，代码会在渐变过程中阻塞，直到渐变完成，然后再继续执行后续的代码。
- `ledc_fade_func_install()`: 安装 LED 控制器渐变函数的函数，用于在 LED 亮度渐变过程中提供更加平滑的过渡效果。在 ESP32 上，LED 控制器（LEDC）模块允许你对 LED 灯进行精确控制，包括调整 LED 的亮度、频率和占空比等参数。<br>

`0`：表示 LED 控制器通道的参数。在 ESP32 上，LED 控制器支持多个通道，每个通道可以独立控制一个 LED 灯或其他输出设备。<br>
- crocodie clip 鳄鱼夹
- blip 光点
- knob 旋钮
- Duty cycle（占空比）: 用于描述周期性信号中高电平时间与周期时间之比的参数。它通常用百分比来表示，表示高电平在整个周期中所占的比例。
![short&long duty](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/short%20duty%20and%20long%20duty.png)<br>
- PWM(Pulse Width Modulation): allows us to drive an output harder or softer. can be used in speed control, diming lights, etc.
- Dimming lights: 调光灯，通过调整灯光的亮度来实现不同光照效果的过程。<br>
在传统的灯具中，通常只有两种状态：开和关。而调光灯则具备在亮度范围内可调节灯光亮度的功能，用户可以根据需求将灯光调节为较亮或较暗的状态，从而实现不同的照明效果。<br>

调光灯可以通过多种方式实现调光效果，其中一些常见的方式包括：<br>
1. **旋钮调光**：通过旋转调光开关或旋钮来调节灯光的亮度。<br>
2. **遥控调光**：通过遥控器来控制灯光的亮度。<br>
3. **触摸调光**：通过触摸灯具或触摸面板来调节灯光的亮度。<br>
4. **智能调光**：通过智能手机应用或智能家居系统来远程控制灯光的亮度，实现定时调光或自动调光等功能。<br>

调光灯具提供了更多的灯光控制选项，可以根据不同场景或个人喜好调节灯光亮度，增强灯光的灵活性和实用性。调光功能在家庭、商业场所、娱乐场所等地方得到广泛应用，带来更加舒适和节能的照明体验。



