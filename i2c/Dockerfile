FROM ubuntu:22.04

RUN apt-get update
RUN apt-get install i2c-tools nano git libi2c-dev libeigen3-dev cmake build-essential g++ -y

RUN mkdir /Adafruit_BNO055
COPY CMakeLists.txt /Adafruit_BNO055/CMakeLists.txt
COPY Adafruit_BNO055/Adafruit_BNO055.h /Adafruit_BNO055//include/Adafruit_BNO055.h
COPY Adafruit_BNO055/Adafruit_BNO055.cpp /Adafruit_BNO055/src/Adafruit_BNO055.cpp
COPY read_from_sensor.cpp /Adafruit_BNO055/read_from_sensor.cpp
COPY Adafruit_BNO055/utility /Adafruit_BNO055/include/utility

COPY Adafruit_Sensor/Adafruit_Sensor.h /Adafruit_BNO055/include/Adafruit_Sensor.h
COPY Adafruit_Sensor/Adafruit_Sensor.cpp /Adafruit_BNO055/src/Adafruit_Sensor.cpp

COPY Adafruit_BNO055/pi4_i2c_bus.h /Adafruit_BNO055/include/pi4_i2c_bus.h
COPY Adafruit_BNO055/pi4_i2c_bus.cpp /Adafruit_BNO055/src/pi4_i2c_bus.cpp

RUN ls /Adafruit_BNO055/include

WORKDIR /Adafruit_BNO055
RUN mkdir build

WORKDIR /Adafruit_BNO055/build
RUN cmake ..
RUN make
RUN ls -ltrh

STOPSIGNAL SIGINT

ENTRYPOINT ["/Adafruit_BNO055/build/read_from_sensor"]
