# Intro
- run esp32 on an emulator

# Docker Container - directory ".devcontainer"
1. Google "Docker" and Install
2. run QEMU instance


# QEMU Project
1. Create a new directory <br>
   Create a new project: ESP-IDF: New Project
   Choose ESP-IDF Board: ESP-WROVER-KIT 3.3V
   Choose Template
2. ESP-IDF: sample_project
3. Write code
4. Open in the remote-container(F11)
5. Compile
6. Debug
![debug](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/debug.png)


# Words
- ELF（Executable and Linkable Format）: 通用的二进制文件格式，用于表示可执行文件、共享库、目标文件等。<br>
ELF 文件包含了程序的机器码、数据、符号表、调试信息等各种信息。它有助于操作系统加载和执行程序，以及在运行时进行调试和符号解析。<br>
ELF 文件的结构通常分为多个部分，包括头部（Header）、节表（Section Table）、段表（Program Header Table）等。头部包含了文件的基本信息，节表和段表则描述了文件中各个节和段的位置和大小。
- external 外部的
- `bin` 文件: 二进制文件的一种常见扩展名，它包含了机器可执行的二进制代码。二进制文件是计算机可以直接执行的程序文件，其中的指令和数据以二进制形式编码。<br>
- build: 广义的术语，它指的是将源代码转换为可执行文件或其他输出文件的过程。在这个过程中，源代码经过编译、链接等处理，生成最终的输出文件，例如二进制文件、库文件、可执行文件等。<br>
因此，"bin" 文件通常是 "build" 过程的输出之一，特指生成的二进制文件。
- Drive is a .exe
- wonky 古怪的
- `pdMS_TO_TICKS` : 在 FreeRTOS 中用于将毫秒转换为时钟节拍数的宏，以便于在定时器、延时等功能中使用。<br>
在 FreeRTOS 中，时间是以时钟节拍（tick）的形式来表示的。每个时钟节拍的时长由 FreeRTOS 的配置决定，通常是以毫秒为单位。因此，要将毫秒转换为时钟节拍数，需要使用宏 `pdMS_TO_TICKS`。<br>

定义：
```c
#define pdMS_TO_TICKS( xTimeInMs ) ( ( TickType_t ) ( ( ( TickType_t ) ( xTimeInMs ) * ( TickType_t ) configTICK_RATE_HZ ) / ( TickType_t ) 1000 ) )
```
其中，`xTimeInMs` 是要转换的毫秒数，`configTICK_RATE_HZ` 是 FreeRTOS 的时钟节拍频率（每秒钟的节拍数）。该宏的计算将 `xTimeInMs` 乘以节拍频率，然后除以 1000，得到对应的时钟节拍数。
- Brilliant!~
- ESP32 QEMU（Quick Emulator）: 用于模拟 ESP32 处理器的开源模拟器。它允许开发者在计算机上模拟运行 ESP32 程序，而无需实际的 ESP32 开发板。这样，开发者可以在更方便的环境中进行程序开发、调试和测试。<br>
ESP32 QEMU 提供了对 ESP32 处理器的模拟，包括 CPU、内存、外设等，因此可以在模拟器中运行 ESP32 的固件和程序。开发者可以在模拟器中调试代码、查看变量、单步执行程序等，从而更好地理解程序的执行过程和调试问题。<br>
使用 ESP32 QEMU，开发者可以节省硬件成本和时间，并且可以在不同的操作系统和环境中进行开发，而不仅限于 ESP32 开发板的平台。它对于学习和熟悉 ESP32 开发，特别是对于初学者来说，是一个很有用的工具。

请注意，虽然 ESP32 QEMU 可以模拟 ESP32 的大部分功能，但并不是完美的仿真。在某些情况下，特别是涉及到硬件相关的操作时，可能需要在实际的 ESP32 开发板上进行验证。
- get cracking with the thing 搞砸这件事
- Github Wiki is very good!



