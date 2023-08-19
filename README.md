# digital_compass
firmware, cad, and documentation for my digital compass project


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
