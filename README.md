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

### Bring an image
```bash
docker pull [IMAGE NAME]:version
```

### Delete an image
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

<br>

## Docker Compose commands

### Initialize and build containers (in background)
```bash
docker compose up -d --build
```
✅ Starts and builds the containers in detached mode.

### Stop all containers
```bash
docker compose stop
```
✅ Stops the containers created with Docker Compose but does not remove them.

### Start stopped containers
```bash
docker compose start
```
✅ Starts containers that were previously stopped.

### Stop and remove containers, networks, volumes
```bash
docker compose down
```
✅ Stops and removes containers, networks, and other resources created by Docker Compose.

### Show status of containers
```bash
docker compose ps
```
✅ Displays the status of the containers managed by Docker Compose.

### View logs in real-time
```bash
docker compose logs -f
```
✅ Shows the logs of all containers in real-time.

### Execute a command inside a container
```bash
docker compose exec [SERVICE NAME] [COMMAND]
```
✅ Runs a command inside an active container managed by Docker Compose.

### List container IDs
```bash
docker compose ps -q
```
✅ Returns only the IDs of the containers (useful for scripts).

### Build or rebuild images
```bash
docker compose build
```
✅ Builds the images defined in the `docker-compose.yml` without starting the containers.

### View docker-compose configuration
```bash
docker compose config
```
✅ Displays the final configuration after resolving variables and includes.
