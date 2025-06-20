# list_docker_commands

<img src="https://github.com/rodrigosistemas/list_docker_commands/blob/main/images/docker.png?raw=true" alt="Docker logo">

---

## Information commands

### See the images
```bash
docker images
````

### Pull an image

```bash
docker pull [IMAGE NAME]:version
```

### Delete an image

```bash
docker image rm [IMAGE NAME]:version
```

### Build an image from a Dockerfile

```bash
docker build -t [IMAGE NAME]:version .
```

---

## Container commands

### Create containers

(You must already have an image)

```bash
docker create [IMAGE NAME]:version
```

```bash
docker container create [IMAGE NAME]:version
```

### Run a container (create + start)

Creates **and** starts a container from an image in one step:

```bash
docker run --name [CONTAINER NAME] [IMAGE NAME]:version
```

### Run a container in background (detached)

```bash
docker run -d --name [CONTAINER NAME] [IMAGE NAME]:version
```

### Start containers

```bash
docker start [CONTAINER ID or NAME]
```

### Show running containers

```bash
docker ps
```

### Show all containers (running + stopped)

```bash
docker ps -a
```

### Stop running containers

```bash
docker stop [CONTAINER ID or NAME]
```

### Add a custom name when creating a container

```bash
docker create --name [CONTAINER NAME] [IMAGE NAME]:version
```

---

## Useful commands

### Convert image to container and run

```bash
docker run [IMAGE NAME]:version
```

### Convert image to container and run in background

```bash
docker run -d [IMAGE NAME]:version
```

### Display container output (logs)

```bash
docker logs [CONTAINER ID]
```

---

## Docker Compose commands

### Initialize and build containers (detached)

```bash
docker compose up -d --build
```

✅ Starts and builds the containers in detached mode.

### Stop all containers

```bash
docker compose stop
```

✅ Stops the containers created with Docker Compose but does **not** remove them.

### Start stopped containers

```bash
docker compose start
```

✅ Starts containers that were previously stopped.

### Stop and remove containers, networks, volumes

```bash
docker compose down
```

✅ Stops **and** removes containers, networks, and other resources created by Docker Compose.

### Show status of containers

```bash
docker compose ps
```

✅ Displays the status of the containers managed by Docker Compose.

### View logs in real time

```bash
docker compose logs -f
```

✅ Streams logs from all containers in real time.

### Execute a command inside a container

```bash
docker compose exec [SERVICE NAME] [COMMAND]
```

✅ Runs a command inside an active container managed by Docker Compose.

### List container IDs only

```bash
docker compose ps -q
```

✅ Returns only container IDs (useful for scripts).

### Build or rebuild images

```bash
docker compose build
```

✅ Builds the images defined in `docker-compose.yml` without starting the containers.

### View the resolved docker-compose configuration

```bash
docker compose config
```

✅ Displays the final configuration after resolving variables and includes.

---

## Network commands

### List available networks

```bash
docker network ls
```

✅ Shows all networks (built-in and user-defined).

### Inspect a network

```bash
docker network inspect [NETWORK NAME | ID]
```

✅ Displays driver, subnet, connected containers, options, rules, and more.

### Create a custom bridge network

```bash
docker network create [NETWORK NAME]
```

✅ Creates a `bridge` network (default).
🔧 **Advanced example with parameters**

```bash
docker network create \
  --driver bridge \
  --subnet 172.25.0.0/16 \
  --gateway 172.25.0.1 \
  my_bridge
```

### Connect an existing container to a network

```bash
docker network connect [NETWORK NAME] [CONTAINER NAME | ID]
```

✅ Adds an additional interface to the container (multi-homing).

### Disconnect a container from a network

```bash
docker network disconnect [NETWORK NAME] [CONTAINER NAME | ID]
```

✅ Removes the network from the container without stopping it.

### Remove a network

```bash
docker network rm [NETWORK NAME | ID]
```

✅ Deletes the network (only if no containers are still attached).

### Prune unused networks

```bash
docker network prune
```

✅ Deletes all networks that have no containers attached.

---

### Quick commands when creating / running containers

| Scenario                           | Command                                                              |
| ---------------------------------- | -------------------------------------------------------------------- |
| Run in a **specific network**      | `docker run --network=[NETWORK NAME] --name [CONTAINER] [IMAGE]:tag` |
| Use the host’s network stack       | `docker run --network host …`                                        |
| Isolate completely (loopback only) | `docker run --network none …`                                        |

---

### Advanced networks (optional)

| Driver      | Creation example                                                                                       | Typical use case                                             |
| ----------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------ |
| **overlay** | `docker network create -d overlay my_overlay`                                                          | Connect services across multiple hosts (Docker Swarm).       |
| **macvlan** | `docker network create -d macvlan --subnet 192.168.1.0/24 --gateway 192.168.1.1 --parent eth0 pub_net` | Containers appear on the physical LAN with their own IP/MAC. |
