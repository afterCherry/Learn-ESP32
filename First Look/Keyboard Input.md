# Keyboard Input
- a character captured from the keyboard
```C++
#include <string.h>

c=getchar();
```
- an array of characters or a string
- Until press enter key
```C++
While(c!='\n'){
  ...
}
```
- no character is found, it will go to be 0xff
```C++
if(c!=0xff){
  ...
}
```
- set delay to give time to the keyboard input and make watchdog timer doesn't get upset
![keyboard input](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/keyboard%20string%20input.png) <br>
The running result is correct. <br>
![input](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/input.png) <br>
![correct printf](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/correct%20printf.png) <br>


# Words
- make watchdog timer doesn't get upset: 意思是采取措施或编写代码，以确保在系统正常运行时定期更新或喂狗，防止看门狗定时器超时并导致系统复位或错误处理。
- cater for 迎合
- spin 旋转
- Carriage return: 一个术语，用于描述光标或打印头在文本行中返回到起始位置的动作。在计算机中，它通常表示为回车符（CR）
- memset(str, 0, sizeof(str)) 的作用是将字符数组 str 中的每个元素都设置为零，以清除其中的垃圾值。memset 是按字节进行填充的，因此对于字符数组，使用零值进行填充将所有元素都设置为 null 终止字符（\0），以表示字符串的结束。这在处理字符串时非常有用。
- char str[100] 有 rubbish: 如果在声明字符数组 char str[100] 之后没有对其进行初始化或填充操作，那么数组中的内容将是未定义的，可能包含垃圾值（rubbish）。
在C++中，未初始化的局部变量（包括数组）的值是不确定的，它们的初始内容取决于存储在内存中的上一个值。这些垃圾值可以是之前在同一内存位置上存储过的任何值。
- from time to time 时不时
