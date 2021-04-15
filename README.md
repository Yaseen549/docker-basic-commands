### Docker Basic commands

<h4>Checking Docker Version</h4>
```docker version```

<h4>Checking detailed information</h4>
```docker info```

<b>Note</b>
- Docker images can be downloaded from Docker hub using docker commands.

Lets pull an image from docker hub using pull command.

### Download a image from docker hub
```
docker pull <<image name>> 
e.g. docker pull nginx
```

### Verify the downloaded docker images:
```
docker images ↵
```
### View all the commands that were run with an image via a container.
```
docker history <<Image Name>>  ↵
e.g. docker history nginx
```
### Remove Docker Images
```
docker rmi <<Image Name>>  ↵
e.g. docker rmi nginx
```
### Download and run an image in docker container using run command
```
docker run <<Image Name>>  ↵
e.g. docker run --name nginxservice -d nginx
```
```
--name --> to specify a name for the running service. In this example, it is nginxservice

-d --> to run the service in the background
```

## Docker Search
- We can also search for the images in the Docker Hub registry by using <b><i>docker search</i></b> subcommand. Let us search for <b><i>ubuntu</i></b> images in the Docker Hub, and limit the search result only to 20 because we have more than 2000 images on Ubuntu:
```
docker search ubuntu | head -20
```


# Docker Commands - Container
## Now lets run list of commands on the service/ container
### List running containers

```docker ps```

### Know the IP address of the running container:
```
docker inspect <container name> ↵
eg: docker inspect nginxservice
```
### Print the stats for a running Container
```
docker stats running <<container name>> ↵
e.g. docker stats nginxservice
```
### Pause the processes in a running container
```
docker pause <<container name>> ↵
e.g. docker pause nginxservice
```
### Unpause the processes in a running container
```
docker unpause <<container name>> ↵
e.g. docker unpause nginxservice
```
### Kill the processes in a running container
```
docker kill <<container name>> ↵
e.g. docker kill nginxservices
```
### Start the same container:
```
docker start <<Container Name>> ↵
e.g. docker start nginxservice
```
### Stop the running container
```
docker stop <<Container Name >> ↵
e.g. docker stop nginxservice
```
## List all containers (This includes containers in a all states):

### We will be able to see the container we just stopped listed here.
```
docker ps -a 
```
### Delete a container:
```
docker rm <<Container Name >> ↵
e.g. docker rm nginxservice
```
### To remove all stopped containers:
```
docker container prune 
```

<b>Note:</b>
- Instead of using the Container Name, all the above commands can be executed with the container id as well.

### Export a container
```
docker export <<Container Name>> <<file_Name>>.tar ↵
e.g. 
- Lets run a service using docker run command.
docker run --name newnginxservice -d nginx
docker export newnginxservice > test.tar
```
### Import a container
```
docker import <<Remote URL/Image Name.tar>>  ↵
e.g. docker import test.tar
```
### Stop Docker daemon process
```service docker stop  ```
### Start Docker daemon process
```service docker start ```
<b>Note:</b>
- You may not be able to try these 2 commands since you would not have access to root on Katacoda playground.

## Diagnose Run Issues
In case you are having a problem with downloading the images and running them, please follow these steps to check whether the docker service is running on your system or not:

- Check the running status of docker:
```service docker stats```
- Restart Docker service in your system:
```service docker restart```

