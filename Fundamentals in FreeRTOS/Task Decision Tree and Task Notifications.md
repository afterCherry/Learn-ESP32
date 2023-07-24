# Semaphore
Someone needs to block or unblock a task, I don't care who.

# Queue
I need to pass data from one task to another.

# Event group
Multiple things needs to happen before I unblock a task.

# Task Notification
Communicate direcly with another task. I care about counting or sending simple data.
```C++
// a sender to notify something
void sender(void * params)
{
    while (true)
    {
      xTaskNotifyGive(receiverHandler);
      xTaskNotifyGive(receiverHandler);
      xTaskNotifyGive(receiverHandler);
      xTaskNotifyGive(receiverHandler);
      vTaskDelay(5000 / portTICK_PERIOD_MS);
    }
    
}

void receiver(void * params) 
{
  while (true)
  {
    // No delay here
    // Just to wait the xTaskNotifyGive has triggered
    int count = ulTaskNotifyTake(pdTRUE, portMAX_DELAY);
    printf("received notification %d times\n", count);
  }
  
}

void app_main(void)
{
   xTaskCreate(&receiver, "sender", 2048, NULL, 2, &receiverHandler);
}
```

```C++
// only binary data
void sender(void *params)
{
  while (true)
  {
    xTaskNotify(receiverHandler, (1 << 0), eSetBits);
    xTaskNotify(receiverHandler, (1 << 1), eSetBits);
    vTaskDelay(1000 / portTICK_PERIOD_MS);
    xTaskNotify(receiverHandler, (1 << 2), eSetBits);
    xTaskNotify(receiverHandler, (1 << 3), eSetBits);
    vTaskDelay(1000 / portTICK_PERIOD_MS);
  }
}

void receiver(void *params)
{
  uint state;
  while (true)
  {
    // first parameter: clearbit 0xffffffff- clear all bits
    xTaskNotifyWait(0xffffffff, 0, &state, portMAX_DELAY);
  }
}
```


# Words
- showcase 展示
- scenario
- xTaskNotify(receiverHandler, (1 << 0), eSetBits);<br>
1. receiverHandler：这是接收者任务的句柄（handle），它用于指定要接收通知的任务。<br>
2. (1 << 0)：这是通知的值，通常用于传递一些信息给接收者。在这里，使用了位运算，将1左移0位，得到值为1。<br>
3. eSetBits：这是一个枚举值（enumeration），用于指定通知的操作。在这里，eSetBits表示设置通知位（Set Bits）。这意味着发送者向接收者发送通知时，会将通知值（即上面的(1 << 0)）设置到接收者的通知位上。<br>
- Function fired: 表示函数被触发或执行的意思
- indication 指示
- Notification 通知
- mutex 互斥体
