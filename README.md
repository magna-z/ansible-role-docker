docker
---

Install (on Debian) and configure Docker Engine.


### Links:
- <https://docker.io>


### Variables:
- **docker_dockerhub_username** и **docker_dockerhub_password** - Username and password for DockerHub access.
- **docker_network_manage_disable** *(default=false)* - Disable network manage (`--iptables=false --ip-forward=false --ip-masq=false`) and use only `--network=host`.
- **docker_internal_network** - Docker internal network name.
- **dockerd_force_restart** *(default=false)* - Force restart docker daemon when any containers is running.
