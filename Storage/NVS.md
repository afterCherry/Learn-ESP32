# Simple Data
```C++
// Initialize the flash
nvs_open("store", NVS_READWRITE, &handle);
...
nvs_close(handle);
```

# Custom Partition
menu config <br>
![partition](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/partition.png)


# Structured Data
```C++
ESP_LOGI(TAG, "cat name: %s, age %d, id %d", cat.name, cat.age, cat.id);
```



# Words
- retrieve 取回
- `nvs_get_blob`: 从 NVS 存储中读取一个指定键（Key）对应的二进制数据，并将其保存到一个指定的缓冲区中。这个函数允许读取任意大小的二进制数据，因为它使用缓冲区来存储读取的数据，而不需要预先知道数据的大小。<br>

```C
esp_err_t nvs_get_blob(nvs_handle_t handle, const char *key, void *out_value, size_t *length);
```
handle: NVS 的句柄（handle），用于标识要操作的特定 NVS 存储区域。在使用 NVS 之前，需要通过 nvs_open 函数打开 NVS，并获取一个有效的 NVS 句柄。<br>
key: 字符串参数，表示要读取的数据项的名称（Key）。<br>
out_value: 一个指向缓冲区的指针，用于存储读取的二进制数据。读取的数据将保存在这个缓冲区中。<br>
length: 一个指向整数变量的指针，用于传递缓冲区的大小（即期望读取的数据的最大长度）。在调用 nvs_get_blob 之前，应该将这个变量设置为缓冲区的大小。读取成功后，length 变量将被更新为实际读取的数据长度。<br>
- 在 NVS（Non-Volatile Storage，非易失性存储）中存储结构化数据有很多用途和好处: <br>
1. **保存配置信息**：结构化数据通常用于保存配置信息，例如设备的网络设置、用户选项、系统参数等。通过将这些配置信息以结构化的方式存储在 NVS 中，可以在设备断电或重启后保留这些信息，从而在下次启动时恢复配置。<br>
2. **固件升级信息**：在进行固件升级时，可以将一些固件版本信息、升级状态等结构化数据存储在 NVS 中，以便在升级过程中进行状态跟踪和恢复。<br>
3. **数据缓存**：在某些场景下，可以将一些临时的结构化数据缓存在 NVS 中，以避免频繁读写外部存储介质，提高数据访问的速度。<br>
4. **存储日志和事件**：可以使用结构化数据来存储设备的日志和事件记录，以便后续分析和故障排除。<br>
5. **用户数据**：将一些用户数据，如个人设置、用户配置等，以结构化方式存储在 NVS 中，便于管理和维护。<br>

在使用 NVS 存储结构化数据时，需要注意以下事项：<br>
**数据结构定义**：首先需要定义好要存储的结构化数据的数据结构，即C/C++中的结构体（Struct）或类（Class）。结构体可以包含不同类型的数据成员，例如整数、浮点数、字符串等。<br>
**数据序列化与反序列化**：将结构化数据存储到 NVS 中时，需要进行数据序列化（将数据转换为字节流）；从 NVS 中读取数据时，需要进行数据反序列化（将字节流还原为结构化数据）。这样可以确保数据正确保存和读取。<br>
**数据访问和错误处理**：在访问 NVS 数据时，要注意处理可能出现的错误情况，例如数据不存在、读写错误等。可以使用 ESP-IDF 提供的错误处理宏（例如 `ESP_ERROR_CHECK`）来方便地检查并处理错误。<br>
- envious 羡慕
- `ESP_ERROR_CHECK(nvs_flash_init_partition("MyNvs")) `:
nvs_flash_init_partition: 在特定的 NVS 分区中进行初始化。它允许您指定要使用的 NVS 分区名称，以便在该分区中初始化 NVS 存储。<br>

"MyNvs": 这是一个字符串参数，用于指定要初始化的 NVS 分区的名称。分区名称是您在使用 NVS 时自定义的名称，用于标识不同的存储区域。在执行 NVS 操作之前，需要使用 nvs_flash_init_partition 函数初始化至少一个 NVS 分区。<br>

ESP_ERROR_CHECK: 这是一个 ESP-IDF 提供的宏，用于检查 ESP-IDF API 调用的返回值，并在发生错误时触发断言。它是一种方便的方式，用于检查 API 调用是否成功执行，如果出现错误，则会在控制台输出错误信息并中止程序执行。注意，此宏仅在调试模式下起作用，发布版本将被省略。<br>
- kick in 起作用
- `erase_flash`: 擦除整个芯片的闪存，清空其中所有内容。
`flash`: 将编译后的程序或数据烧录到芯片的闪存中，使芯片能够执行相应的程序或读取数据。
- `nvs_commit(handle)`: 将对 NVS 存储区进行的修改提交到非易失性存储介质（如闪存或EEPROM）上，以确保数据的持久化保存。<br>
在使用 NVS 进行数据读写操作时，所有的修改都是在内存中进行的，而没有直接写入到非易失性存储介质上。为了避免频繁写入闪存，造成性能下降和寿命损耗，ESP-IDF 提供了一种缓冲的机制，只有在调用 nvs_commit(handle) 函数时，才会将内存中的修改真正写入到闪存中。<br>
- `ESP_ERR_NVS_NOT_FOUND`: NVS（Non-Volatile Storage，非易失性存储）操作返回的一个错误代码。它表示在 NVS 中找不到指定的数据项或键（Key）。<br>
通常情况下，开发者在使用 NVS API 之前，应该先确认要读取的数据项是否存在，避免出现 ESP_ERR_NVS_NOT_FOUND 错误。可以使用 nvs_get_i32() 函数的返回值来检查是否发生了 ESP_ERR_NVS_NOT_FOUND 错误，并做相应的错误处理。<br>
- `nvs_get_i32(handle, "val", &val)`: 从 NVS 中读取一个名为 "val" 的整数值，并将其存储在变量 `val` 中。<br>

`handle`: NVS 的句柄（handle），用于标识要操作的特定 NVS 存储区域。在使用 NVS 之前，需要通过 `nvs_open` 函数打开 NVS，并获取一个有效的 NVS 句柄。<br>
`"val"`: 字符串参数，表示要从 NVS 中读取的数据项的名称（Key）。<br>
`&val`: 存储在 `val` 指向的变量中。<br>
