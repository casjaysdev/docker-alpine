## 👋 Welcome to alpine 🚀  

alpine README  
Base image of AlpineLinux  
  
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
--name casjaysdev-alpine \
--hostname alpine \
-e TZ=${TIMEZONE:-America/New_York} \
casjaysdev/alpine:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdev/alpine
    container_name: casjaysdev-alpine
    environment:
      - TZ=America/New_York
      - HOSTNAME=alpine
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdev/alpine
```
  
OR
  
```shell
git clone "https://github.com/casjaysdev/alpine" "$HOME/Projects/github/casjaysdev/alpine"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdev/alpine"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdev: [Github](https://github.com/casjaysdev) [Docker](https://hub.docker.com/u/casjaysdev) ⛵  
