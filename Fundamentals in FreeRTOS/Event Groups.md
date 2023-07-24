```C++
#include "freertos/event_groups.h"

EventGroupHandle_t evtGrp;
// flags to indicate whether to listen http or bluetooth
const int gotHttp = BIT0;
const int gotBLE = BIT1;

void listenForHTTP(void *params)
{
  while (true)
  {
    xEventGroupSetBits(evtGrp, gotHttp);
    printf("got http\n");
    vTaskDelay(2000 / portTICK_PERIOD_MS);
  }
}

void listenForBluetooth(void *params)
{
  while (true)
  {
    xEventGroupSetBits(evtGrp, gotBLE);
    printf("got BLE\n");
    vTaskDelay(5000 / portTICK_PERIOD_MS);
  }
}

// Both of 2 tasks
void task1(void *params)
{
  while (true)
  {
    // wait for both
    xEventGroupWaitBits(evtGrp, gotHttp | gotBLE, true, true, portMAX_DELAY);
    printf("received http and BLE\n");
  }
}

void app_main(void)
{
  evtGrp = xEventGroupCreate();
}

```


# Words
- instantiate 实例化
- Event groups can operate off multiple indicators: 事件组可以根据多个指示器（indicators）进行操作。<br>
在编程和多线程应用中，事件组是一种同步机制，用于实现任务之间的同步和通信。事件组允许多个任务（或线程）等待一组特定的事件发生，从而实现任务的协调和同步。指示器是用于标识某个事件是否发生的信号或标志。例如，可以将某个特定的位或变量作为指示器，当它的值为1时表示相应的事件已经发生。<br>
这种机制在编程中常常用于处理复杂的任务协调和同步需求，允许多个任务等待多个事件的发生，并在满足条件时执行相应的操作。<br>
