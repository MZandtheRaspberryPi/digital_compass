### Pi Setup
I used Ubuntu 22.04. I flashed an image using raspberry pi imager, which let me configure user and wifi. Then, I did:

```
ssh-keygen # generate and copy key to github
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh --dry-run # remove dry run flag when want to run
sudo usermod -aG docker $USER
sudo reboot

docker run hello-world
```

```
git clone git@github.com:MZandtheRaspberryPi/digital_compass.git --recurse-submodules
```

### Calibrating

Datasheet [here](https://cdn-shop.adafruit.com/datasheets/BST_BNO055_DS000_12.pdf) has section 3.10 on calibrating.

For accelerometer, "6 different stable positions for a period of few seconds to allow the accelerometer to calibrate."

For gyro: "Place the device in a single stable position for a period of few seconds to allow the gyroscope to calibrate."

For mag: "the steps mentioned below are to calibrate the magnetometer for hard-iron distortion (...) Compass, M4G & NDOF_FMC_OFF: Make some random movements (for example: writing the number ‘8’ on air) until the
CALIB_STAT register indicates fully calibrated."


