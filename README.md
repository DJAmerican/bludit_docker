# Bludit Docker Image (Alpine based)
You can run Bludit as a Docker container. Image based in Alpine Linux latest, php 8.1 (with healthcheck) and latest bludit. The size of container only 32 MB !


### Run the container

```
$ docker run --name bludit -p 8004:80 -d djamerican/bludit_docker:latest
```

To get access go with your browser to http://localhost:8004

### Stop the container

```
$ docker stop bludit
```

### Delete the container

```
$ docker rm bludit
```

### Delete the image

```
$ docker rmi djamerican/bludit_docker:latest
```

### Start with docker-compose

```
version: '3.0'
services:
  bludit:
    image: djamerican/bludit_docker
    ports:
      - 8004:80
    volumes:
      - html:/var/www           # Bludit home dir
      - nginx:/etc/nginx        # Nginx config dir
    restart: always
    cpu_shares: 50
    mem_limit: 64m
    memswap_limit: 64m
volumes:
  html: {}
  nginx: {}
networks:
  default:
```

### Refs
- Bludit home - https://www.bludit.com/ (Edi Goetschel, tnx for the great work !)

- Original Blidit container - https://hub.docker.com/u/bludit (Centos + php7 based)

