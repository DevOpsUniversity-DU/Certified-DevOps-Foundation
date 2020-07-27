Docker Cheat Sheet:

Docker Containers
	docker search  # search the images in docker hub
	docker pull    # pull image from docker hub
	docker images  # list the images in local
	docker run (interactive / detached ) # run a container from an image
	docker ps      # list the running containers 
	docker ps -a   # list running + exited containers
	docker inspect # inspect a container
	docker stop|start|restart   # stop/start/restart a container 
	docker rm / docker rm -f    # remove the containers from the server
	docker exec    # get inside a running container 

Docker Images 
	docker images  # list images in local
	docker commit  ( manual )  # create image from container changes 
	docker build ( automated ) # create image using a dockerfile
	docker history # view the layers of an image
	docker inspect # inspect an image
	docker rmi     # remove image from local

image repository 
	docker hub (public)  # docker image reporsitory 
	docker registry container (private) # docker image repository open source 
	DTR (priviate)  # docker image repository licensed tool from docker org 
		docker login  # login to image repo from commad line
		docker tag    # create alias name for an image in local
		docker push   # push images to docker image repository
