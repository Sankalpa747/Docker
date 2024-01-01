### To create the docker image
    docker build .

### To run the docker container (Attached mode)
    docker run -p 3000:80 <IMAGE_ID>

### To run the docker container (Detached mode)
    docker run -p 3000:80 -d <IMAGE_ID>

### To start the docker container (Restart) (Detached mode)
    docker start <CONTAINER_NAME>

### To start the docker container (Restart) (Attached mode)
    docker start -a <CONTAINER_NAME>

### To attach with the detached container
    docker attach <CONTAINER_NAME>

### To check the logs (Including past logs)
    docker logs <CONTAINER_NAME>

### To attach and check the logs (Including past logs)
    docker logs -f <CONTAINER_NAME>