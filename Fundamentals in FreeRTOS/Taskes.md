RTOS(Real Time Operator System) is a basic block that we can build in application with ESP-IDF, for example we can do multiple task and make them execute at the same time, we can get task intertalk with each other.<br>
https://www.freertos.org/zh-cn-cmn-s/Documentation/RTOS_book.html <br>

# Tasks
Consider each task is individual 

## For project
- read data
```C++
// pass the position
void task1(void * params)
{
  while (true)
  {
    printf("reading temperature from %s\n", (char *) params);
    vTaskDelay(1000 / portTICK_PERIOD_MS); // every second
  }
}

void app_main(void)
{
   xTaskCreate(&task1, "temperature reading", 2048, "task 1", 2, NULL); // 2048 memory; 2-the second priority 1-the lowest priority
}
```

# Words
- x task return something; vtask return void
- humidity 湿度
- modular 模块化的
- schedule
- tutorial 教程
- surrogate 代理
- concatenate 连接
- a couple of 几个
- daunting 令人畏惧的
- excellent insight
- companion 伴侣
