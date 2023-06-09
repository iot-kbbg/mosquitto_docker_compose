# Readme

The readme explains how to set up a Mosquitto server with Docker-compose on a raspberry pi.

## Setup Docker

### update system
~~~
sudo apt-get update
sudo apt-get upgrade
~~~

### install docker
~~~
sudo curl fsSL https://get.docker.com | sh
~~~
### add user to docker group
~~~
sudo usermod -aG docker ${USER}
~~~

### install dependencies for deocker-compose
~~~
sudo apt-get install libffi-dev libssl-dev python3-dev python3 python3-pip
~~~

## Setup Docker-compose

### install docker-compose with pip
~~~
sudo pip3 install docker-compose
~~~

### enable docker as a service
~~~
sudo systemctl enable docker
~~~

### reboot the raspberry pi
~~~
sudo reboot
~~~

## start the server

To start the server, clone this repository to your home folder on the raspberry pi and navigate to the folder where the docker-compose.yml is:
~~~
git clone https://github.com/iot-kbbg/mosquitto_docker_compose.git
cd mosquitto_docker_compose
~~~

Then execute the following command:
~~~
sudo docker-compose up -d
~~~

The mosquitto server should now be online.
You can use the software MQTT Explorer to connect to the server's IP on port 1883:
http://mqtt-explorer.com/

You can check the logs of the containers with the command:
~~~
docker-compose logs
~~~

To see all running docker containers, use the command:
~~~
docker ps
~~~

The included config file has a very basic setup with no security at all. 
for the full list of options you can check the documentation of the mosquitto config files on:
https://mosquitto.org/man/mosquitto-conf-5.html
