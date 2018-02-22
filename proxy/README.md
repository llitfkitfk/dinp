# Quick start

## deploy tls proxy

```bash

docker stack deploy -c docker-compose.yml proxy
```

## mv tls client cert to local machine

```bash

rsync -azvh root@remote-docker-hostname:/var/lib/docker/volumes/proxy_client-data/_data/.docker/ ./.docker/
```

## setup local tls remote control

```bash

export DOCKER_CERT_PATH=./.docker
export DOCKER_HOST=tcp://remote-docker-hostname:2376 
export DOCKER_TLS_VERIFY=1
```

## test

```bash

docker ps
```