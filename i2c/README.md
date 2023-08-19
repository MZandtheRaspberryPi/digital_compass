```
docker build -t i2c_test .
docker run -it --device /dev/i2c-1 --entrypoint=/bin/bash i2c_test
i2cdetect -y 1

```
