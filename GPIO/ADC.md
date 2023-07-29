
There are two ADC channels we can use. The first one got 8 channels, the second one got 10 channels. <br>
![2 ADC channels](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/2%20ADC%20channels.png) <br>

light sensor registor for voltage divide calculator, which is 5 kilo-ohms in brightess and 10-kilo-ohms in darkness.
![voltage divide calculator](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/voltage%20divider%20calculator.png) <br>

```C++
#include "driver/adc.h"

adc1_config_width(ADC_WIDTH_BIT_12);
adc1_config_channel_atten(ADC1_CHANNEL_0, ADC_ATTEN_DB_0);
```

![resistor](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/resistor.png) <br>
![result calculator](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/calculator.png) <br>
![light brightness control resistor](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/light%20sensor%20control%20brightness.png) <br>




# Words
- 9-12bit: 12bit is the maximum resolution
- calibrate 校准



