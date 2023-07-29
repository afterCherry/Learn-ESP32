# Intro
- I2C=IIC=Inter Integrated Circuit is a communication protocol that consists of two lines- SCL(clock line) and SDA(data line). 
- Multiple devices on the same bus, such as humanity sensor, temperature sensor and pressure sensor.
- one master and many slaves.
- 2 I2C buses
- either bus can act as a master or slave
- configurable GPIO for SDA and SCL
- Each device has one or more registers
- Sometimes you need to write to a register as a command before being read
![i2c](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/i2c.png)


# LM75A
temperature sensor
![lm75a](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/lm75a.png)
![device40](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/device%2040.png)

# Words
- Tile sensor: 泛指一类常用于测量物理量或环境参数的传感器。<br>

具体而言，"Tile sensor" 可以包括以下类型的传感器：<br>
1. **加速度传感器（Accelerometer）**：用于测量物体的加速度，可以用来检测物体的运动、震动和倾斜等。<br>
2. **陀螺仪传感器（Gyroscope）**：用于测量物体的角速度或角度变化，可以用于姿态控制和导航应用。<br>
3. **磁场传感器（Magnetometer）**：用于测量周围磁场的强度和方向，常用于指南针和地磁导航应用。<br>
4. **温度传感器（Temperature Sensor）**：用于测量环境的温度，广泛应用于各种温度监测和控制场景。<br>
5. **湿度传感器（Humidity Sensor）**：用于测量环境的湿度水平，常用于气象监测和温湿度控制应用。<br>
6. **光照传感器（Light Sensor）**：用于测量环境的光照强度，常用于自动照明和环境光感应应用。<br>
7. **气压传感器（Pressure Sensor）**：用于测量大气压强，常用于气象监测和高度测量应用。<br>


