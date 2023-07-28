# Wear leveling and CRUD


# Read only
## CMakeLists.txt
```C++
# FAT WL
# fatfs_create_spiflash_image(storage ../flash-loaded FLASH_IN_PROJECT)

# FAT RO
fatfs_create_rawflash_image(storage ../flash-loaded FLASH_IN_PROJECT)
```

# Words
- `esp_vfs_fat_spiflash_mount_rw_wl(BASE_PATH, "storage", &esp_vfs_fat_mount_config, &wl_handle)`: 在 ESP32 或 ESP8266 微控制器上挂载 FAT 文件系统的函数调用。<br>

解释每个参数的含义：<br>
1. `BASE_PATH`：FAT 文件系统挂载的基本路径。它是用于指定挂载的文件系统在文件系统树中的基本路径，可以是任何合法的路径。<br>
2. `"storage"`：这是指定要挂载的 FAT 文件系统的分区标签或名称。在挂载之前，你需要在磁盘上有一个 FAT 文件系统分区，该参数用于指定要挂载的分区。<br>
3. `&esp_vfs_fat_mount_config`：这是一个指向 `esp_vfs_fat_mount_config_t` 结构体的指针，用于配置 FAT 文件系统的挂载选项。通过该结构体，你可以配置文件系统的大小、簇大小等参数。<br>
4. `&wl_handle`：这是一个用于保存挂载句柄的指针。在挂载成功后，该句柄可以用于后续对 FAT 文件系统的操作。<br>

综合起来，这段代码的作用是将一个事先格式化好的 FAT 文件系统分区挂载到 ESP32 或 ESP8266 微控制器上，并使得文件系统可以在指定的 `BASE_PATH` 下被访问和使用。这样，你就可以使用文件操作 API 在挂载的文件系统中读写文件，实现对文件的存储和读取等功能。
- Wear leveling（磨损均衡）:用于延长闪存存储设备（如固态硬盘、闪存驱动器等）寿命的技术。在闪存存储设备中，每个存储单元（例如NAND闪存芯片）的擦写寿命是有限的。当数据频繁地在存储单元上进行写入和擦除时，某些存储单元可能会过早失效，从而导致整个设备的寿命缩短。<br>

为了解决这个问题，闪存设备采用了"wear leveling"技术。这种技术的主要目标是尽可能平均地分配写入和擦除操作到所有的存储单元中，避免某些存储单元频繁被写入和擦除，从而均衡地分摊磨损。这样做的结果是，设备的寿命得到了有效延长，提高了闪存设备的耐久性和可靠性。<br>

具体实现wear leveling的方式有多种，其中一些常见的方法包括：<br>
1. **块级wear leveling**：将数据写入不同的闪存块，而不是总是写入相同的块，以确保块之间的擦写次数均衡。<br>
2. **页级wear leveling**：将数据写入不同的页，而不是总是写入相同的页，以确保页之间的擦写次数均衡。<br>
3. **动态wear leveling**：通过实时监测每个存储单元的使用情况，动态地调整数据的写入位置，以实现更加均衡的擦写操作。<br>

通过采用wear leveling技术，闪存设备可以更加均匀地利用每个存储单元，降低某些区域的过度使用，从而提高设备的寿命和可靠性。这对于经常进行大量写入操作的存储设备，特别是固态硬盘等闪存设备来说尤为重要。
