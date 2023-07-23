# Debug Steps
1. Put a breakpint: what is in the process and what's happening in the memory, which help us to see why is this situation
2. "bug" button on the left to debug
3. step forward to see the address
4. Step click in function updatePerson, we will see the address of variable "person" to see whether the calling "person" is consistent with the definition "person"


# Structure
```C++
#include <string.h>

typedef struct Person_struct {
  char firstName[20];
  char lastName[20];
  int age; 
} Person;
```

```C++
void updatePerson(Person *person, char * dataRetrieved)
{
  strcpy(person->firstName, "data from dataRetrieved");
  strcpy(person->lastName, "data from dataRetrieved");
  person->age = 35;
}
```

- No rubbish when debugging is the best thing all over the world.
- Just put the mouse on the variable, we will see the properties of the variable.

# Array
```C++
void exclamIt(char * phrase){
  strcat(phrase, "!");
}

exclamIt(phrase);
printf("function output: %s\n", phrase);
```




# Words
- open bracket closed bracket 开括号，闭括号
- mutate 变异
- exclamation 感叹号
- ampersand &
- whereas 然而
- collapse 坍塌
- arrow expression —>
- squiggly 蜿蜒的
- strcpy: allocate a new memory, 原因如下：<br>
目标字符串长度未知：strcpy函数会将源字符串复制到目标字符串中，但目标字符串的长度是不确定的。为了保证目标字符串能够完整地容纳源字符串，需要分配足够的内存空间。<br>
避免缓冲区溢出：如果目标字符串的内存空间不足以容纳源字符串，可能会导致缓冲区溢出，破坏其他内存区域的数据，甚至引发安全漏洞。<br>
动态长度字符串：有时候，源字符串的长度是在运行时才能确定的，例如从用户输入或其他外部数据获取。为了能够正确复制变长的字符串，需要动态分配足够的内存。<br>
So in order to get the orifinal address, we use the pointer.
- allocate 分配
- ramp up 斜坡上升
- Arduino: 一种开源的硬件开发板平台和软件环境，用于制作和开发各种交互式电子项目，旨在使电子制作和编程变得简单易学，适合初学者和专业人士。<br>
Arduino开发板由一个微控制器、输入输出引脚和其他组件组成，可以用于控制各种电子设备和执行各种任务。用户可以通过Arduino开发板连接传感器、执行器、显示器等外部设备，编写简单的代码来控制这些设备的行为。Arduino的编程语言基于C/C++。<br>
Arduino的开源性质使得用户可以自由获取和修改其硬件和软件设计，而且有大量的开源库和社区支持，使得用户可以轻松分享和交流项目和经验。<br>
Arduino广泛应用于各种电子制作项目，包括智能家居系统、机器人、交互式艺术装置、自动化控制等。由于其简单易用的特点，它成为了学习电子制作和编程的理想平台，也受到了广大爱好者和专业人士的喜爱。
