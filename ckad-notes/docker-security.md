## How to SSH to docker container shell ?

```
docker ps

docker exec -it <container name> /bin/bash

```

## How to run docker with different user ?

```
docker run -d --user=1000 ubuntu sleep 2000 

```
