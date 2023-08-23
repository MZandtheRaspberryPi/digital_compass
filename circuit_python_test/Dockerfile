FROM ubuntu:22.04

RUN apt-get update
RUN apt-get install python3 python3-pip nano git wget -y

RUN python3 --version

RUN python3 -m pip install adafruit-circuitpython-lsm6ds adafruit-circuitpython-lis3mdl adafruit-circuitpython-bno055 RPi.GPIO adafruit-extended-bus 

COPY ./example_bno055.py /example_bno055.py
RUN chmod +x /example_bno055.py
COPY ./example_lsm6ds0x_lis3mdl.py /example_lsm6ds0x_lis3mdl.py
RUN chmod +x /example_lsm6ds0x_lis3mdl.py
