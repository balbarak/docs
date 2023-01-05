# Docker Commands

### List runing Containers
`sudo docker ps`

### List all Containers
`sudo docker ps -a`


### Run Container Silent
`sudo docker run -it -d "image-name"`
### Stop Container
`sudo docker stop "container name"`

### Run bash cli inside docker image
`sudo docker exec -it "container id" bash`

### Expose docker port to host port
`sudo docker run -it -d -p hostPort:containerPort "image name"`

### Copy files to container
`sudo docker cp <path> containerId:<path>`
Ex
`sudo docker cp /home/data 9028843:/home/files`

### Clean images 
`docker system prune`

### Remove all images
`docker system prune -a`
