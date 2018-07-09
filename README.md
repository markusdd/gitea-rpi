# gitea-rpi

This Dockerfile is for Automated Builds on Docker Hub.

## Usage with SQLite Database or External DB
```
$ docker run -d \
  --restart=always \
  --name=gitea-arm \
  -p 22:22 \
  -p 3000:3000 \
  -v /opt/gitea:/data \
  markusdd/gitea-rpi:latest
```
## Usage with linked Database
```
$ docker run -d \
  --restart=always \
  --name=gitea-arm \
  --link mariadb:mysql \
  -p 22:22 \
  -p 3000:3000 \
  -v /opt/gitea:/data \
  markusdd/gitea-rpi:latest
```
## Usage with custom options (for Example NGINX Proxy and Letsencrypt)
```
$ docker run -d \
  --restart=always \
  --name=gitea-arm \
  --link mariadb:mysql \
  -e VIRTUAL_HOST=git.sample.com \
  -e VIRTUAL_PORT=3000 \
  -e LETSENCRYPT_HOST=git.sample.com \
  -e LETSENCRYPT_EMAIL=info@sample.com \
  -p 22:22 \
  -p 3000:3000 \
  -v /opt/gitea:/data \
  markusdd/gitea-rpi:latest
```
## Resources
* [Docker Hub](https://hub.docker.com/r/markusdd/gitea-rpi/)
* [Github](https://github.com/markusdd/gitea-rpi/)
