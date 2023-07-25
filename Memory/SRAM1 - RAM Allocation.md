- 2 Parts:
DRAM: allocate memory when we compile, for dynamic malloc variables stack <br>
IRAM(Instruction):Interrupts <br>
单位：bytes

```C++
make -j8 flash monitor
就是 idf.py flash monitor

make size
就是 idf.py size

// size for .data, .bss, Flash, rodata...
make size-files
就是 idf.py size-files
```
![allocate](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/allocate.png)
![memory](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/memory.png)

# Words
- MINGW（Minimalist GNU for Windows）: 目标是为Windows开发者提供一个类Unix的开发环境，使他们能够使用类似于Linux或Unix系统上的GNU工具进行开发。它可以让开发者在Windows上编写和编译C、C++等程序，而无需额外的设置或复杂的配置。
- .bss: 特殊的段（section）名称，在编译和链接过程中用来表示未初始化的全局或静态变量所占用的内存空间。这些变量在程序运行之前并没有被初始化，因此在内存中的初始值是未定义的。.bss 段中的变量通常被初始化为零或空值。

在嵌入式系统或其他资源有限的环境中，.bss 段中的变量可以在程序运行时动态地分配内存，而不需要在编译时预先分配固定的内存空间。这样可以节省内存空间，并且避免不必要的内存浪费。
- `xPortGetFreeHeapSize`: 获取当前空闲堆内存的大小。它返回一个数值，表示当前堆内存中可供分配的未使用内存大小。
- `heap_caps_get_free_size`: 获取特定类型的堆内存的可用空间大小，帮助开发者在运行时监测内存的使用情况，以便及时进行内存管理和优化。。<br>
ESP32 芯片具有多种类型的内存，例如内部RAM、外部PSRAM等。每种类型的内存都有不同的用途和特点。

函数的原型如下：
```c
size_t heap_caps_get_free_size(heap_caps_handle_t heap);
```
参数 `heap` 是堆内存的类型，可以是以下值之一：<br>
`MALLOC_CAP_DEFAULT`: 默认堆内存 <br>
`MALLOC_CAP_INTERNAL`: 内部RAM <br>
`MALLOC_CAP_SPIRAM`: 外部PSRAM <br>
其他类型，根据具体的芯片和配置可能还包含其他选项 <br>

函数的返回值是堆内存中当前可用的空间大小，以字节为单位。通过调用这个函数，您可以了解特定类型的堆内存的使用情况，进而根据需要做出相应的内存管理决策。
- heap 堆
- datagram 数据报
- underneath the hood 在引擎盖下面
- Metal shield 金属屏蔽罩: 用于电子设备中的金属外壳，旨在提供电磁屏蔽和防护。这种屏蔽罩通常用于保护电路板、芯片和其他敏感的电子组件，防止它们受到外部电磁干扰或静电放电的影响。
