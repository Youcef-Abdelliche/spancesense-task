# spacesense-task
## Setup project

### Pre-requisites

Make sure you have the following pre-installed components:

- [Docker](https://docs.docker.com/get-docker/)

### Build Docker image
Run this command to build docker image
```bash
docker build --name mycontainer -d taskimage
```

### Run container
Run this command start running container
```bash
docker start mycontainer
```

### Get address IP
Run this command to get address IP and start sending requests
```bash
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' mycontainer
```

