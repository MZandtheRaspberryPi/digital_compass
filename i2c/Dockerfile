FROM ubuntu:22.04

RUN apt-get update
RUN apt-get install i2c-tools nano git -y

ENTRYPOINT ["i2cdetect", "-y", "1"]
