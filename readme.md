# Readme

The readme explains how to set up a Mosquitto server with Docker-compose on a raspberry pi.

## Setup Docker

### update system
'Sudo apt-get update
Sudo apt-get upgrade'

### install docker
'Sudo curl fsSL https://get.docker.com | sh'

### add user to docker group
'Sudo usermod -aG docker ${USER}'

### install dependencies for deocker-compose
'Sudo apt-get install libffi-dev libssl-dev python3-dev python3 python3-pip'

## Setup Docker-compose

### install docker-compose with pip
'Sudo pip3 install docker-compose'

### enable docker as a service
'Sudo systemctl enable docker'

## start the server

To start the server, clone this repository to your home folder on the raspberry pi and navigate to the folder where the docker-compose.yml is:
'git clone https://github.com/goossensbas/mosquitto_docker_compose.git
cd mosquitto_docker_compose.git'

Then execute the following command:
'sudo docker-compose up -d'

The mosquitto server should now be online.
You can use the software MQTT Explorer to connect to the server's IP on port 1883:
http://mqtt-explorer.com/

You can check the logs of the containers with the command:
'docker-compose logs'

To see all running docker containers, use the command:
'docker ps'

The included config file has a very basic setup with no security at all. 
for the full list of options you can check the documentation of the mosquitto config files on:
https://mosquitto.org/man/mosquitto-conf-5.html
