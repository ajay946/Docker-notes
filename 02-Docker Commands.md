# Some basic docker commands

**To list running containers**
- docker ps       

**To list all the containers with their history**
- docker ps -a     

**To list only the container id of running containers**
- docker ps -q    

**To pull an image from docker hub**
- docker pull image_name     

**To run an image in detached mode(background)**
- docker run -d image_name    

**To run an image with an interactive terminal and login to /bin/bash**
- docker run -it image_name /bin/bash    

**To do port binding/mapping (base:container)**
- docker run -p 80:80 nginx      
>Enable inbounds in security group for base port

**login to docker**
- docker login      

**To create an new image**
- Dockerfile

```
FROM ubuntu
Run apt-get update
Run apt-get install python
Run pip install flask
Run pip install flask-mysql
COPY . /opt/source-code
ENTRYPOINT FLASK_APP=/opt/source-code/app.py flask run

```   


**To build the Dockerfile created**
- docker build Dockerfile -t username/my-custom-app

**To list out all the docker images present in host**
- docker images         

**To stop a running containers**
- docker stop container_name      

**To remove a container(can use -f for force remove)**
- docker rm container_name        

**To remove an image from the host**
- docker rmi image_name           

**To push our own docker image to dockerhub repository**
- docker push image_name        

**To check history of a docker image**
- docker history image_name     

**To show details of an image in json format**
- docker inspect image_name     

**To take a backup of container data**
- docker run -v /usr/local/tomcat -d -p 8080:8080 --name process_1 tomcat        

**To list all attached volumes**
- docker volume ls      

**To run a command on the container without using run command**
- docker exec -ti container_id pwd        

**To sync the volume(volume mapping)**
- docker run -d -v /root/tomcat/_data:/usr/local/tomcat -p 9090:8080 --name process_2 tomcat     



**To create own bridge network for DNS service**
- docker network create -d bridge --subnet 10.10.10.0/24 ajay-bridge

**To run a new container on the newly created bridge network**
- docker run -d --name c3 --network ajay-bridge tomcat
