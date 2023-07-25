# Windows Environment for Openocd
- openOCD is in the ESP tool chain, which has been added to the environment variables in Windows, so we can call openocd for any directory
![command](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/command.png)
![openocd](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/openocd.png)
# Download Zadig 
Options - Devices

# launch.json
- .vscode -> launch.json
- validate "miDebuggerPath"
- idf.py build -> "build" directory 



# Words
- biolerplate 样板文件
- Zadig: 用于在 Windows 操作系统上安装和配置 USB 驱动程序的免费软件。<br>
在 Windows 中，许多 USB 设备都需要安装特定的驱动程序才能与计算机正常通信和工作。有些设备可能自带了适用于 Windows 的驱动程序，但有些设备可能需要手动安装或更新驱动程序。此时，Zadig 就发挥了作用。<br>
使用 Zadig，用户可以轻松地更改 USB 设备的驱动程序。它提供了一个简单的界面，允许用户选择 USB 设备，并选择要安装的驱动程序。通常，用户可以选择将设备的驱动程序更改为 WinUSB 驱动程序，这是一种通用的 USB 驱动程序，适用于许多 USB 设备。<br>
Zadig 的使用非常方便，它可以帮助用户解决一些 USB 设备在 Windows 中无法正常工作的问题，同时也方便开发者进行 USB 设备的测试和调试。但需要注意的是，更改 USB 设备的驱动程序可能会导致设备在其他操作系统中无法正常工作，因此在使用 Zadig 之前应谨慎备份设备的原始驱动程序。
- VID (Vendor ID) 和 PID (Product ID) 是 USB 设备的两个重要标识符。<br>
1. VID (Vendor ID)：厂商识别码，用于标识 USB 设备的制造商。它是一个由 USB 实施者论坛 (USB Implementers Forum, USB-IF) 分配的 16 位十六进制数字，每个厂商都有唯一的 VID。<br>
2. PID (Product ID)：产品识别码，用于标识 USB 设备的具体产品型号。PID 也是由 USB-IF 分配的 16 位十六进制数字，每个设备型号都有唯一的 PID。PID 和 VID 结合在一起可以唯一地标识一个 USB 设备。<br>

VID 和 PID 是 USB 设备在计算机上被识别和配置的关键信息。当插入一个 USB 设备时，计算机会读取设备的 VID 和 PID，并根据这些信息选择适当的驱动程序和配置，以确保设备正确工作。<br>
- openocd/script/board/.cfg: configuration file
- invoke 调用
- `xtensa-esp32-elf-gdb` : 用于 ESP32 开发板的 GDB （GNU Debugger）调试器 <br>
对于 ESP32 开发，由于 ESP32 是使用 Xtensa 处理器架构，因此使用特定于该架构的 GDB。<br>
它允许开发者在开发板上调试 ESP32 的程序，包括查看变量的值、跟踪代码执行、设置断点等操作。

