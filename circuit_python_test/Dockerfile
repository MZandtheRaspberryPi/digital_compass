FROM ubuntu:22.04

RUN apt-get update
RUN apt-get install python3 python3-pip nano git wget -y

RUN python3 --version

RUN python3 -m pip install --upgrade adafruit-python-shell
RUN wget https://raw.githubusercontent.com/adafruit/Raspberry-Pi-Installer-Scripts/master/raspi-blinka.py
RUN python3 raspi-blinka.py

RUN python3 -m pip install adafruit-circuitpython-bno055 RPi.GPIO

COPY ./example.py /example.py