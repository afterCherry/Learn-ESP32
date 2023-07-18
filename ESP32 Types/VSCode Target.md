# Change chip
Click esp32 button, and you can see the project name.
![esp32-c3](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/here%20should%20be%20esp32-c3.png)
![project name](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/project%20name.png)
![wanted chip](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/wanted%20chip.png)
![delicate choice](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/dedicated%20choice.png)

# IDF terminal

```C++
idf.py
```
![list targets](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/list%20the%20target.png)
![set target](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/set%20target%20for%20paticular%20target.png)

With the command, we can do a lot of things, for example list all the targets it supported and set particular target...So we can specify the command,
```C++
idf.py --list-targets
```
![list all targets](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/list%20all%20targets.png)
Try to compile.
```C++
idf.py flash monitor
```
Everytime we change targets, it does a full clean.
We will see the work successfully.
![work correctly](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/work%20correctly.png)






# Words
- delicate 精美的
- dedicated 投入的
- manually 手动地
- ESP USB Bridge 提供了一种简单而方便的方式，使开发人员能够直接通过 USB 连接与 ESP32 和 ESP8266 进行通信和控制。它通过虚拟串口（Virtual Serial Port）的方式，将计算机的 USB 接口转换为与 ESP32/ESP8266 微控制器通信所需的串行接口。
- ESP-PROG 是一种调试和编程工具，用于断点调试、单步执行、寄存器观察、存储器访问等。
- USB JTAG 是一种连接电子设备的接口标准，用于进行调试、编程和测试等操作。JTAG (Joint Test Action Group) 是一组用于测试和调试集成电路的标准接口和协议。USB JTAG 则是通过 USB 接口实现 JTAG 连接的方式。
- plug in 插入
