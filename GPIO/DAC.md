![dac current register](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/dac%20resistor.png) <br>

```C++
#include "driver/dac.h"

dac_output_enable(DAC_CHANNEL_1); // GPIO25
dac_output_voltage(DAC_CHANNEL_1, 200); // set value
```

Control the brightness by the voltage value <br>
![dac calculate](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/dac%20calculate.png) <br>

- value =255 <br>
![255 voltage](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/255%20voltage.png) <br>

- value =200 <br>
![200 voltage](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/200%20voltage.png) <br>


- value =195 <br>
![195 voltage](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/195%20voltage.png) <br>
