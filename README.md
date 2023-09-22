# list_docker_commands

<img src="https://github.com/rodrigosistemas/list_docker_commands/blob/main/images/docker.png?raw=true" alt="Docker logo">

## Information commands

### Docker version info
```bash
docker version
```

### Show info like number of containers
```bash
docker info
```

## Image commands

### See the images
```bash
docker images
```

## Bring an image
```bash
docker pull [IMAGE NAME]:version
```

## Delete an image
```bash
docker image rm [IMAGE NAME]:version
```

## Container commands

### Create containers
To create a container it is necessary to have an image

```bash
docker create [IMAGE NAME]:version
```

```bash
docker container create [IMAGE NAME]:version
```

### Start containers
```bash
docker start [CONTAINER ID]
```

### See containers in execution
```bash
docker ps
```

### See all containers
```bash
docker ps -a
```

### Stop containers in execution
```bash
docker stop [CONTAINER ID]
```

### Add a container name
```bash
docker create --name [CONTAINER NAME] [IMAGE NAME]
```

## Useful commands

### Convert image to container and run
```bash
docker run [IMAGE NAME]:version
```

### Convert image to container and run in background
```bash
docker run -d [IMAGE NAME]:version
```

### Display the output of a container
```bash
docker logs [CONTAINER ID]
```
