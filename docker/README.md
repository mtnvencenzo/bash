
# Docker Bash Utilities

This directory contains bash scripts for common Docker management tasks, including installation, cleanup, monitoring, GPU support, and Docker Compose operations. All scripts are tested on Ubuntu 24.04 but should work on most modern Linux distributions.

## Portainer setup
To run the portainer ui for docker management follow the instructions below.  

[portainer docker hub](https://hub.docker.com/r/portainer/portainer-ce)  
[portainer github](https://github.com/portainer/portainer)

```bash
sudo docker volume create portainer_data

sudo docker run -d \
    --name=portainer \
    --restart=unless-stopped \
    -p 8000:8000 \
    -p 9000:9000 \
    -p 9443:9443 \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v portainer_data:/data \
    portainer/portainer-ce
```

```bash
# Open in chrome
google-chrome http://localhost:9000
```