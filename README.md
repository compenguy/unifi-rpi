# unifi-rpi
A docker container with the unifi controller for the raspberry pi (or compatible armhf targets)

# Getting Started
## Docker version
The "docker.io" package in the raspbian jessie repositories is too old to be useful.

[Hypriot](http://blog.hypriot.com/downloads/) has armhf debian packages for raspberry pi.  Download the latest, and install it with `dpkg --install docker-hyprio_1.10.3-1_armhf.deb".

```
wget https://downloads.hypriot.com/docker-hypriot_1.10.3-1_armhf.deb
sudo dpkg --install docker-hypriot_1.10.3-1_armhf.deb
```

## Getting the Dockerfile
```
git clone https://github.com/compenguy/unifi-rpi.git
cd unifi-rpi
cd unifi5
```

## Building the docker container
```
docker build -t="willpage/unifi-rpi:unifi5" --rm --no-cache .
```

## Starting the app
```
docker run --net=host -d willpage/unifi-rpi:unifi5
```

# Important configuration information
## Volumes:
### `/var/lib/unifi`
Configuration data
### `/var/log/unifi`
Log Files
### `/var/run/unifi`
Runtime State Files
## Environment Variables:
### `TZ`
Timezone (e.g. America/Los_Angeles)
## Ports:
### 8080/tcp
### 8081/tcp
### 8443/tcp
### 8843/tcp
### 8880/tcp
### 3478/udp

# Credits
[rednut](https://github.com/rednut/docker-unifi-controller), whose work helped me get started down the right path
[umiddelb](https://github.com/umiddelb/armhf/wiki/Get-Docker-up-and-running-on-the-RaspberryPi-(ARMv6)-in-four-steps-(Wheezy)) for his instructions on getting docker installed on the rpi
[resin](https://hub.docker.com/r/resin/rpi-raspbian/) for his raspbian/jessie base image
[ubnt](https://help.ubnt.com/hc/en-us/articles/220066768-UniFi-Debian-Ubuntu-APT-howto) for caring about us linux folk
[jacobalberty](https://github.com/jacobalberty/unifi-docker/) for his Dockerfile and instructions, of which what you see here is only a minor variation.



