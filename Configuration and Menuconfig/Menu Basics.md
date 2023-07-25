Own configuration loaded into the chip

```C++
idf.py menu config
```
![visualized config](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/visualized%20config.png)



# Words
- 
- `sdkconfig`:配置文件，用于存储项目的编译配置选项。<br>
在 ESP-IDF 中，项目的配置信息需要保存在一个配置文件中，以便在编译过程中进行参考。这些配置选项可以包括启用或禁用某些组件、调整堆栈大小、配置串口波特率、选择默认的 Wi-Fi SSID 和密码等。<br>
一旦配置选项被修改，`sdkconfig` 文件会被自动更新。在进行项目编译时，ESP-IDF 将读取 `sdkconfig` 文件中的配置选项，并根据这些选项进行编译，从而生成适合您项目的可执行文件。<br>
使用 `sdkconfig` 文件可以方便地定制 ESP-IDF 项目的编译配置，从而满足不同项目的需求。该文件的存在使得配置选项可以轻松地在不同的项目之间共享和重用。
- Passphrase: 用于保护无线网络（Wi-Fi）安全的密码，由多个单词、数字和符号组成的字符串，通常比较长且复杂，以增加网络的安全性。<br>
当您设置无线路由器或访问点时，需要指定一个 Passphrase 作为网络的密码。然后，连接到该无线网络的设备必须输入正确的 Passphrase 才能成功连接到网络。<br>
Passphrase 在无线网络中起到了加密和认证的作用。它通过加密数据传输，防止未经授权的设备访问网络，从而保护网络安全。较长和复杂的 Passphrase 使得破解网络密码更加困难，增加了网络的安全性。因此，Passphrase 是保护 Wi-Fi 网络安全的重要组成部分。<br>
- SSID（Service Set Identifier 网络名称）: 用于识别无线网络的唯一名称，类似于有线网络中的网络名称。<br>
当您在设备上搜索可用的无线网络时，会看到一系列的 SSID 列表，这些列表列出了周围可用的无线网络名称。用户可以从这些列表中选择要连接的无线网络。在设置无线路由器或访问点时，您可以指定 SSID 作为网络的名称。连接到同一个 SSID 的设备将在同一个局域网内进行通信，从而实现无线网络的连接和通信。<br>
- `idf.py menuconfig`:启动配置菜单界面，让开发者可以方便地对项目进行配置。<br>
在 ESP-IDF 中，项目的配置信息通常存储在 `sdkconfig` 文件中，该文件定义了编译时的各种配置选项，例如启用或禁用某些组件、调整堆栈大小、配置串口波特率等。通过编辑 `sdkconfig` 文件，可以自定义项目的编译配置。<br>
而 `idf.py menuconfig` 命令则提供了一个交互式的菜单界面，让开发者可以直接在终端中配置项目，而无需手动编辑 `sdkconfig` 文件。在菜单界面中，开发者可以通过上下箭头键选择配置选项，并通过回车键进入子菜单或修改选项的值。<br>
- `.bat`: 批处理文件的文件扩展名，也称为批处理脚本或批处理程序。它是一种在 Windows 操作系统中常见的脚本文件格式，用于执行一系列命令或操作。<br>
批处理文件是一种文本文件，其中包含一系列的命令，这些命令会按顺序执行。批处理文件可以包含各种命令和操作，例如设置环境变量、运行程序、复制文件、删除文件等。<br>
- IDF terminal: automatically runs a script inside the IDF, called "export.bat"
- underneath the hood 在引擎盖下面

