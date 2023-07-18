# Download and Install the ESP IDF
 1. Search for "esp32 getting started", and then we will go to the official document.
 ![get started](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/esp32%20getting%20strated.png)
 ![windows](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/windows.png)
 ![Installer](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/installer.png)<br>
 2. Get the online installer.<br>
 3. Windows Defender: Here already exists a registry entry into your registry keys which tell Windows Denfender not 
 scan files that being built by ESP IDF.<br>
 ![defender](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/windows%20defender.png)
 Never forget to Click "Apply Fixes"
 4. Choose the latest version(try). Release/v4.3 is safe.One os for IDF, and the other is for extension build tools.
 ![version](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/version.png)
 ![name](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/Name%20local%20directory.png)
 Choose additional features and funtionalities. Click all.
 ![feature1](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/feature1.png)
 ![feature2](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/feature2.png)
 ![finish](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/finish.png)
 Play with command to see typical project directory.
 ![command](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/command.png)
# integrate IDF into VS Code(Visual Studio Code)
With extensions, it can do a lot. We go to install "Espressis IDF" plugin. <br>
![esp](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/idf.png) <br>
![C++](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/C%2B%2B.png) <br>
Know the capabilities and configurations.
![capabilities](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/esp%20idf%20capability.png) <br>
![configuration](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/configure.png) <br>
Go to start-up page.
![start-up](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/startup%20page.png) <br>
Choose "Espress" <br>
Create a project directory locally. <br>
![option](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/option.png) <br>
Create a new project.<br>
![new project](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/new%20project.png) <br>
Choose Custom board, ESP32-S2 board. <br>
![board](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/board.png) <br>
Click "Create project using template ...", click "Yes" after been successful. <br>
![sample project](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/sample_project.png) <br>
There are a lot of files on the left, and the main.c is the main file when developing.
Go to setting.json. Click pencil and Choose "Default" for "C_Cpp.intelliSenseEngine" <br>
![click to default](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/setting%20default.png) <br>
Some buttons on the bottum. The "ESP-IDF Flash device" help to download the project to the chip. "Monitor device" give the output of chip. "Command shell" is very useful.<br>
In the shell, "idf.py build" "idf.py flash monitor" <br> Flash means automatically build <br>

```C++
print("hello world\n");
```

Press Control, the window will be closed.<br>
![close the window](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/close%20window.png) <br>
Also can use PowerShell locally, and we will see the already commands.
![powershell](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/power%20shell.png) <br>
![powershell command](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/powershell%20command.png) <br>

# words
- square brcket 方括号
- subsequent 随后的
- essential 基本的
- semicolon 分号
- squiggle 花体 
- indication 指示
- exclaim 惊呼
- compilation 汇编
- intellisense 智能感知
- bare 赤裸
- clutter 杂乱
- underscore 下划线
- dash 虚线
- brcket 括号
- spice 香料
- resolve 解决
- palette 调色板
- plugin 插件
- icon pack 图标包
- fingertip 指尖 Put your fingertip on "G".
- top-notch 一流的，拔尖的  The top-notch universities in china are Tsinghua University and Peking Univeristy.
- intellisense IOT equipments have the property of intellisense.
- scroll down 向下滚动 Scroll down the screen and you will see what I want you see.
- wizard 向导 Follow the wizard and you will get what you want to get.
- spin up 旋转 Spin up the ball and enjoy it.
