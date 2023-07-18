# Remote container
We will load a docker image. Docker is a container environment that gives
a virtual system with a linux terminal, also includes built-in idf.
You don't need to install IDEA if you use docker. If you are in a team, please make sure that everybody use the same environment.
![remote connector](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/remote%20connector.png)

# Files
## devcontainer
A virtual environment that makes you feel you're using something
on your machine.
### Dockerfile
- Download the container and Edit version <br>

```C++
FROM espressif/idf:release-v4.3
```

### devcontainer.json
what type of extensions...

## vscode
### c_cpp_properties.json
Put intellisense on the code, for example from the path we can get what files that are available.

### launch.json
### settings.json
### tasks.json

## build
### esp1.bin 
It's convenient to copy to elsewhere to flash a project.

## main
### component.nk
It's for the old make system that we don't need anymore. It's not to be utilized
for the project.
### CMakeLists.txt
- It defines all the files, including source files and head files.
- Add files inside of the project.

## CMakeLists.txt
- It use path to basically reference the cmake file to actually make files.
- Map the project name.
- Add files out of the project

## Makefile
It's non-use, you can delete it.

## sdkconfig
It contains all configurations that we have for esp32. We will use 
various configurations during the project.

- 2 ways to edit the file
  - in the terminal
    ![edit terminal](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/edit%20sdkconfig.png)
  - use setting button. There's a window pop up and go to the new page
    ![search the setting tree](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/search%20the%20setting%20tree.png)

# Words
- overwrite (确实很生动形象
- other than that 除此之外
- brace 大括号
- Command WSL: Windows System Linux
- pertaining 有关的
- pertain 属于
