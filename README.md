## 👋 Welcome to alpine 🚀  

alpine README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update alpine
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/alpine/rootfs"
git clone "https://github.com/dockermgr/alpine" "$HOME/.local/share/CasjaysDev/dockermgr/alpine"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/alpine/rootfs/." "$HOME/.local/share/srv/docker/alpine/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-alpine \
--hostname alpine \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-alpine/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-alpine/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/alpine:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/alpine
    container_name: casjaysdevdocker-alpine
    environment:
      - TZ=America/New_York
      - HOSTNAME=alpine
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-alpine/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-alpine/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/alpine
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/alpine" "$HOME/Projects/github/casjaysdevdocker/alpine"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/alpine"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
