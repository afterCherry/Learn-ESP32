
# For project
The data from the PV Cell can compose to a file.

```C++
  extern const unsigned char indexHtml[] asm("_binary_index_html_start");
  ...
  extern const unsigned char imgEnd[] asm("_binary_pinout_jpg_end");
```

# Makefile 文件
Here all files are included.
 
```C++
COMPONENT_EMBED_TXTFILES := files/index.html
COMPONENT_EMBED_TXTFILES += files/sample.txt // += add another text file
COMPONENT_EMBED_FILES := files/pinout.jpg
```

# CMakeLists.txt
```C++
set(COMPONENT_EMBED_TXTFILES
    "files/index.html"
    "files/sample.txt"
)

set(COMPONENT_EMBED_FILES
    "files/pinout.jpg"
)
```





# Words
- suffix 后缀
- `asm("_binary_index_html_start")`:内联汇编的语法，用于在C/C++代码中访问由编译器内部处理的二进制数据。<br>
在这里，"_binary_index_html_start" 是一个特殊的符号，它代表了一个二进制数据块的起始地址。这个符号是由编译器自动生成的，通常是在编译时将一个二进制文件（比如图片、文本文件、HTML等）转换成C/C++源代码的数组形式。<br>
通常情况下，当我们在编译过程中使用类似的二进制文件时，编译器会自动将文件转换成一个名为 _binary_文件名_start 的数组，并且在一个特殊的区域保存在可执行文件中。这样我们就可以在C/C++代码中使用内联汇编的方式来引用这些二进制数据。<br>
- ".mk" 文件: 用于构建和管理项目的 Makefile 文件。Makefile 是一种文本文件，其中包含了一系列规则和命令，用于指示编译器和构建工具如何编译和构建项目中的源代码文件。<br>
Makefile 文件主要用于在源代码文件发生变化时，自动化地执行编译和构建操作，以生成可执行程序、库文件或其他项目所需的输出文件。它定义了项目中的源代码文件、编译选项、目标文件、依赖关系和生成规则等信息。<br>
通常，".mk" 文件是在使用 GNU Make 工具时的惯例命名。GNU Make 是一个常用的构建工具，用于根据 Makefile 中的规则和指令来构建项目。除了 GNU Make，也有其他构建工具可以读取 ".mk" 格式的文件。<br>
使用 Makefile 可以大大简化项目的构建过程，尤其是在大型项目中，因为它可以自动管理源代码的编译和依赖关系，从而节省开发者的时间和精力。在许多编程语言和开发环境中，都可以使用 Makefile 来管理项目的构建过程。<br>
- file: audio file, image file, text file(string for a html)...
- cetera: "等等" 或 "以及其他"。拉丁文中的词，也可以写作 "caetera"，在英语中通常称为 "et cetera" 或简写为 "etc."。
- raw variable: 某个变量是原始的、未经处理的，或者是指向内存中特定位置的指针 <br>
variable: 更通用的术语，表示在程序中用于存储数据的可变量 <br>
- persistently 坚持不懈地
