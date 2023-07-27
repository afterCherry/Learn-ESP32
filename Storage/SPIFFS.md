# Intro
SPI FLASH FILE SYSTEM: use SPI to talk to the Flash

process:
1. build time: convert a directory into a bin file
2. flash time: load the bin file into flash

# Upload with Flash
- partition(byte)
- read the data we just flashed

```C++
esp_vfs_spiffs_register(&config);
...
esp_vfs_spiffs_unregister(NULL);
```

# Looping Through Files


# Loading Data Scripts
- different configuration for each chip
![bin](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/bin.png)
![file bin](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/file%20bin.png)

# CRUD
Create, Read, Update, Delete



# Words
- squiggly 蜿蜒地
- boilerplate 样板文件
- baud rate 波特率
- whack 重击
- `sys/unistd.h`: unix standard <br>
- `sys/stat.h`: statistics
- `dirent.h`: "Directory Entry Header"，意为目录项头文件。<br>
该头文件包含了一些用于文件和目录操作的函数和定义，使得 C 语言能够进行目录的遍历、文件查找和目录操作等操作。<br>

在标准 C 库中，`dirent.h` 头文件定义了一个结构体 `struct dirent`，以及一些与目录操作相关的函数，最常用的函数是 `opendir()`、`readdir()` 和 `closedir()`。<br>

主要函数和结构体：<br>
`opendir()`：用于打开一个目录，并返回一个指向 `DIR` 结构体的指针。这个指针用于后续对目录的遍历和操作。<br>
`readdir()`：用于读取目录中的项（文件和子目录）。通过调用该函数，可以依次读取目录中的每一个项。<br>
`closedir()`：用于关闭之前由 `opendir()` 打开的目录。释放资源并关闭目录。<br>
`struct dirent`：这是一个结构体，代表目录中的一个条目（即文件或子目录）。这个结构体包含了有关文件或目录的信息，如文件名、文件类型等。<br>

使用 `dirent.h` 头文件中的函数和结构体，可以在 C 语言中进行目录遍历、文件查找和目录操作等操作，方便对文件系统中的目录和文件进行管理和访问。<br>
- `stdio.h`: C 标准库中的一个头文件，其全称是 "Standard Input/Output Header"，意为标准输入/输出头文件。<br>
该头文件包含了一系列用于输入和输出操作的函数和定义，使得 C 语言能够进行与终端、文件和其他设备的输入输出交互。<br>

包括但不限于：<br>
`printf()`：用于向标准输出（通常是终端）打印格式化的输出。<br>
`scanf()`：用于从标准输入（通常是终端）读取格式化的输入。<br>
`fopen()`：用于打开文件。<br>
`fclose()`：用于关闭文件。<br>
`fprintf()`：类似于 `printf()`，但可以将输出写入到指定的文件而不是标准输出。<br>
`fscanf()`：类似于 `scanf()`，但可以从指定的文件读取输入而不是标准输入。<br>
`getchar()`：从标准输入读取一个字符。<br>
`putchar()`：向标准输出打印一个字符。<br>
- esp_vfs_spiffs_conf_t config = {.partition_label = NULL};<br>
不指定 SPIFFS 使用的分区标签时，SPIFFS 将在运行时选择可用的分区来创建文件系统。这样可以在同一个设备上创建多个 SPIFFS 文件系统，而不用担心分区冲突或固定使用一个分区。<br>
动态选择分区的优势在于：<br>
灵活性：可以根据应用需求动态选择合适的分区来存储 SPIFFS 文件系统。不同的应用场景可能需要不同大小的存储空间，动态选择分区可以更好地适应这种灵活性。<br>
容错性：如果指定了固定的分区标签，那么如果该分区发生问题或不可用，可能会导致 SPIFFS 无法正常工作。而不指定分区标签允许在其他可用分区上创建 SPIFFS，从而提高容错性。<br>
多文件系统支持：允许在同一设备上创建多个 SPIFFS 文件系统，可以支持更多的存储需求，例如同时管理用户文件和系统文件。<br>

.format_if_mount_failed = true: 指定在挂载 SPIFFS 文件系统失败时是否进行格式化。
- spiffs_create_partition_image(storage ../spiffs_dir FLASH_IN_PROJECT): <br>
storage: SPIFFS 分区的名称或标识符。在一个系统中，可能存在多个 SPIFFS 分区，每个分区用于存储不同的数据或文件。通过指定 storage 参数，可以选择要创建的具体分区。<br>




../spiffs_dir: 这是 SPIFFS 文件系统的源目录，即要打包成镜像的 SPIFFS 文件系统的内容所在的目录路径。<br>

FLASH_IN_PROJECT: 这是要创建的 SPIFFS 分区镜像的输出文件名，表示镜像将被写入项目中的某个位置，可能是项目的固件文件或其他位置。<br>
- `register_component()`: 将一个组件（component）注册到系统或框架中，以便在系统运行时可以被正确地识别、加载和使用。<br>

具体来说，组件是指系统中可以独立存在、具有特定功能或特性的模块。组件可以是软件库、驱动程序、插件、服务等。通过将组件注册到系统中，系统可以根据需要加载和卸载这些组件，使得系统可以动态地配置、扩展和修改功能。<br>

在组件化开发中，通常有以下几个步骤：<br>
1. **定义组件接口**：首先定义组件的接口，包括组件的名称、功能、参数等。这些接口定义了组件所提供的服务和功能。<br>
2. **实现组件**：根据组件接口的定义，实现具体的组件。不同的组件可以有不同的实现，但它们必须符合接口定义。<br>
3. **注册组件**：将组件注册到系统中，以便系统可以识别和管理这些组件。这通常通过调用类似 `register_component()` 这样的函数来实现。<br>
4. **加载组件**：在系统运行时，根据需要加载组件。这样可以根据用户需求动态选择加载特定的组件，使得系统更加灵活和可配置。<br>
5. **使用组件**：一旦组件被注册和加载，系统可以通过接口调用来使用组件的功能。组件之间可以进行交互和通信，从而实现复杂的功能。<br>

- Flash编程时间：程序或固件烧录到闪存（Flash memory）中所花费的时间。在将固件写入闪存时，通常需要一定的时间来完成烧录操作，这个时间取决于闪存的大小和芯片的速度等因素。<br>

Flash存储时间：数据在闪存中的存储时间，即数据在闪存上保持不变的时间。闪存是一种非易失性存储介质，意味着数据在断电后仍然保持不变，这种数据持久性通常被称为存储时间。<br>

Flash擦除时间：当要在闪存上写入新的数据或固件时，通常需要先将闪存中的数据擦除，然后再写入新的数据。<br>。


- 构建（编译）程序: 目录转换为二进制文件
- 文件系统本身不支持目录: 如果有一个文件系统中不支持目录结构，但允许创建文件名为 "documents/report.txt"，那么 "documents" 可以被视为一个“虚拟目录”，"report.txt" 就是该目录下的一个文件。<br>
虽然实际上没有真正的目录 "documents"，但通过文件名的设置，我们可以使文件看起来好像存在于一个目录下。<br>

