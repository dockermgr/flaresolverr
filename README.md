## 👋 Welcome to flaresolverr 🚀  

flaresolverr README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update flaresolverr
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/flaresolverr/rootfs"
git clone "https://github.com/dockermgr/flaresolverr" "$HOME/.local/share/CasjaysDev/dockermgr/flaresolverr"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/flaresolverr/rootfs/." "$HOME/.local/share/srv/docker/flaresolverr/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-flaresolverr \
--hostname flaresolverr \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-flaresolverr/rootfs/data:/data:z \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-flaresolverr/rootfs/config:/config:z \
-p 80:80 \
casjaysdevdocker/flaresolverr:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/flaresolverr
    container_name: casjaysdevdocker-flaresolverr
    environment:
      - TZ=America/New_York
      - HOSTNAME=flaresolverr
    volumes:
      - $HOME/.local/share/srv/docker/casjaysdevdocker-flaresolverr/rootfs/data:/data:z
      - $HOME/.local/share/srv/docker/casjaysdevdocker-flaresolverr/rootfs/config:/config:z
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/flaresolverr
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/flaresolverr" "$HOME/Projects/github/casjaysdevdocker/flaresolverr"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/flaresolverr"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
