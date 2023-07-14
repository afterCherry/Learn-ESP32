# Inter-Integrated Ciruit protocol｜I squared C
![I2C](https://github.com/afterCherry/Learn-ESP32/blob/main/Images/I2C.png)

## Devices
Multiple Masters and Slaves

## Work
- modes: depend on the reansmission spped, such as standard mode, fast mode, low mode, high-speed mode, ultra-fast mode
- handshake mechanism: ack signal


## Serial communication
split data into bit streams and transmitted along data line

## Compunents
- 2 bidirectional open-drain lines
SDA- Serial DAta line, SCL- serial CLock, both have pull-up resistors <br>
typical oprating voltage: 3.3V 5V
- 112 nodes
limited by address width and total bus capacitance, which also influence the communication distance with a few meters
- Master: synchronize comminication, send and receive data
- Slave: response, send and receive data <br>
The role is flexible, a master can also be a slave.

## Applying for peripherals: 
sacrifice transmission speed to reduce manufacturing costs
- DAC ADC
- monitor：contrast, color banlance, hue 色调｜CPU temperature, fan speed
- LED
- included as a kernel module /usr/include/linux/i2c.h, provides definations and functions.
