
```C++
// 定义一个名为 MY_BOOL 的配置选项，它是一个布尔类型的选项，用户可以选择“是”或“否”
//  bool "select yes or no" 是一个提示字符串，用于在菜单配置界面中显示给用户。当用户进入菜单配置界面时，系统会显示这个提示字符串，提示用户该配置选项是选择“是”还是“否”。
// 用户可以根据自己的需求，在菜单配置界面中选择“是”或“否”，从而定制项目的功能。选择“是”会将配置选项设为打开（即为真），选择“否”会将配置选项设为关闭（即为假）。
config MY_BOOL
    bool "select yes or no"

// help to guide hints of what we actually are trying to do
config MY_STRING
    string "enter a string"
    default "hello world!"
        help
            this is my help text description
```

After typing `idf.py menuconfig` in window IDF-Command
![menuconfig](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/Menuconfig.png) <br>
![visual config](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/visualize%20config.png) <br>

```C++
idf.py menuconfig

idf.py build

idf.py flash monitor
```


# Words
- tricky 棘手的
- `CONFIG_MY_I`: 用于配置整数类型的配置选项
- icon 图标
- encapsulate 封装
- `Kconfig.projbuild`: 在ESP-IDF中用于在项目级别上定义配置选项。<br>
在 ESP-IDF 中，配置选项通常存储在 `sdkconfig` 文件中，包含了 ESP-IDF 的默认配置选项和用户自定义的配置选项。但有时候，我们希望在特定项目中定义一些与默认配置不同的选项，而不影响其他项目的配置。为了解决这个问题，ESP-IDF 允许在项目根目录下创建一个名为 `Kconfig.projbuild` 的文件，只包含与当前项目相关的配置选项，而不包含默认配置选项，可以定义项目特定的配置选项，包括启用或禁用某些组件、调整堆栈大小、配置串口波特率、选择默认的 Wi-Fi SSID 和密码等。<br>
当进行项目配置时，ESP-IDF 会同时读取 `Kconfig` 和 `Kconfig.projbuild` 文件中的配置选项，并将它们合并成一个完整的配置。这样，您就可以在项目级别上定制 ESP-IDF 的配置，而不影响其他项目的配置。
