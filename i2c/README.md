```
docker build -t i2c_test .
docker run -it --device /dev/i2c-1 i2c_test

```
```
mikey@compass:~/digital_compass$ i2cdetect -y 3
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:                         -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- 1c -- -- --
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- 3c -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- 6a -- -- -- -- --
70: -- -- -- -- -- -- -- --
```

# configuring ubuntu
https://hackaday.com/2022/02/01/did-you-know-that-the-raspberry-pi-4-has-more-spi-i2c-uart-ports/
https://forums.raspberrypi.com//viewtopic.php?f=29&t=302381
https://forums.raspberrypi.com/viewtopic.php?t=248439

 Enabling I2C3, with SDA on GPIO4 and SCL on GPIO5
nano /boot/firmware/config.txt
dtoverlay=i2c3,pins_4_5


Dir structure
```
mz@mz-VirtualBox:~/digital_compass/i2c$ tree -L 2
.
├── Adafruit_BNO055
│   ├── Adafruit_BNO055.cpp
│   ├── Adafruit_BNO055.h
│   ├── assets
│   ├── code-of-conduct.md
│   ├── examples
│   ├── examples_processing
│   ├── library.properties
│   ├── LICENSE
│   ├── OBJLoader
│   ├── README.md
│   └── utility
├── Adafruit_Sensor
│   ├── Adafruit_Sensor.cpp
│   ├── Adafruit_Sensor.h
│   ├── examples
│   ├── library.properties
│   ├── LICENSE.txt
│   └── README.md
├── CMakeLists.txt
├── Dockerfile
├── read_from_sensor.cpp
└── README.md

8 directories, 15 files
```
