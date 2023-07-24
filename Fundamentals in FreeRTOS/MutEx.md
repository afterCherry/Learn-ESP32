MutEx(Mutual Exclusion Object)

```C++
#include "freertos/semphr.h" // library

SemaphoreHandle_t mutexBus;

// If my semaphore can take, then I can write to the bus
if (xSemaphoreTake(mutexBus, 1000 / portTICK_PERIOD_MS))
{
  writeToBus("tempratrue is 25c\n");
  xSemaphoreGive(mutexBus);
}


void app_main(void)
{
  mutexBus = xSemaphoreCreateMutex();
}

```




# Words
- arthouse 艺术屋
- flag/ indicator/ 
- Mutual Exclusion 互斥
- semaphore 信号
- exclusion 排除
- mutual 相互的
