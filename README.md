# Docker_2025
Docker_2025 
Commands - Installing Docker
### Installing Docker on Ubuntu ###
 
# uninstalling any old versions
sudo apt remove docker docker.io containerd runc
 
 
#  adding Docker’s official GPG signing key:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
 
 
# adding the official docker repository 
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
 
# refreshing the apt cache
sudo apt update
 
# selecting the docker repository as the default one
apt-cache policy docker-ce
 
# installing docker
sudo apt install docker-ce docker-ce-cli containerd.io
 
# checking its status
sudo systemctl status docker
 
# adding the current user to the docker group to be able to run the docker command
sudo usermod -aG docker ${USER}
 
docker --version

## The Docker CLI ##
## Pulling Images and Running Containers ##
 
# testing the entire installing
docker --version 
docker version
docker info
docker container run hello-world
 
# getting help
docker help
docker MANAGEMENT_COMMAND help => Ex: docker container help
 
# searching for an image on Docker Hub
## docker search IMAGE_NAME
docker search debian
docker search mongo
 
# pulling an image from docker hub
## docker image pull IMAGE_NAME:TAG
docker image pull redis:5.0.10 
docker image pull ubuntu:latest
docker image pull mysql         # => by default tha name of the TAG is latest
 
# listing local images
docker images
docker image ls
 
# running a container
## docker container run OPTIONS IMAGE_NAME
docker container run -P httpd
# equivalent to:
docker container create -P httpd
docker container ls -a  # listing all containers
docker container start CONTAINER_ID
 
# getting a shell into a container
docker container run -it centos  # to detach from the container without stopping it press: Ctrl + P + Q
