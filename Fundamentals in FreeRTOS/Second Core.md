# Multiple cores
Core1 for application that mainly runs tasks; <br>
Core2 for background, like communication, protocols with regards to TCP/IP, connecting to bluetooth.
```C++
void app_main(void)
{
   xTaskCreatePinnedToCore(&task2, "humidity reading", 2048, "task 2", 2, NULL,0);//0- default core, 1- second core
}
```

# Words
- with regards to 关于
