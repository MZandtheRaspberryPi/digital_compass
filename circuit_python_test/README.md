# what is this?
instructions on how to run these docker images to test various adafruit IMUs and make sure we can get data. examples for the lsm6ds0x_lis3mdl and bno055 are included. Could adapt to other varieties by changing the .py file and rebuilding the image (from a pi).

## Install Docker
Run the two commands. on the second command, remove the --dry-run flag after verifying the command re-run it to install docker.
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh --dry-run
```


## Check your I2C setup
Ensure that you can see your devices on your PI outside of docker. I have 3 devices showing up, 2 from my adafruit imu and one from an oled screen.

```
sudo apt-get install -y i2c-tools
i2cdetect -y 1
```
```
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

## Run the Docker Image
The below command will download the image and run it for the lsm6ds0x lis3mdl example. The other command for the other example is below.
```
sudo docker run -it --entrypoint=/example_lsm6ds0x_lis3mdl.py --device /dev/i2c-1 mzandtheraspberrypi/pi4-ada-imu-python:2023-08-23
```

```
Acceleration: X:   0.04, Y:  -0.10, Z:   9.90 m/s^2
Gyro          X:  -0.00, Y:   0.00, Z:   0.00 rad/s
Magnetic      X:   1.48, Y:   9.95, Z: -44.48 uT

Acceleration: X:  -0.01, Y:  -0.08, Z:   9.84 m/s^2
Gyro          X:  -0.00, Y:   0.00, Z:   0.00 rad/s
Magnetic      X:   2.51, Y:   9.68, Z: -44.02 uT

Acceleration: X:  -0.04, Y:  -0.10, Z:   9.86 m/s^2
Gyro          X:  -0.00, Y:   0.00, Z:   0.00 rad/s
Magnetic      X:   2.16, Y:   9.51, Z: -44.27 uT

Acceleration: X:  -0.04, Y:  -0.08, Z:   9.80 m/s^2
Gyro          X:  -0.00, Y:   0.00, Z:   0.00 rad/s
Magnetic      X:   2.21, Y:   9.87, Z: -43.70 uT
```

```
docker run -it --entrypoint=/example_bno055.py --device /dev/i2c-1 mzandtheraspberrypi/pi4-ada-imu-python:2023-08-23
```

## Changing the Image
If you need to make a change to the image, you could change the Dockerfile or the .py files and then re-run the build command from this directory.
```
docker build -t pi4-ada-imu-python .
```
