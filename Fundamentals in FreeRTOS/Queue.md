- There are many structures I can use to the project, such as queue, mutex, semaphore and so on.
- Change the priority to give different order


```C++
#include "freertos/queue.h"

QueueHandle_t queue;

long ok = xQueueSend(queue, &count, 1000 / portTICK_PERIOD_MS);


// parameter3- how long will we want to wait?
if (xQueueReceive(queue, &rxInt, 5000 / portTICK_PERIOD_MS))
{
  printf("doing something with http %d\n", rxInt);
}

void app_main(void)
{
  queue = xQueueCreate(3, sizeof(int));// maximum 3 intergers in the queue
}
```
![tasks on the core](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/run%20on%20the%20core.png)

