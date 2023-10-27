docker
---

Install and configure Docker Engine.


### Links
- <https://docker.io>
- <https://docs.docker.com/engine/install/>


### Variables
- **`docker_apt_repository`** *(type=dict, mandatory)* - Object with struct `{repo_url: "", repo_branch: "stable|test|edge", key_url: "", key_id: ""}`. See [examples](#examples).

- **`docker_network_manage`** *(type=bool, default=true)* - Allow `dockerd` manage network on host. Else `dockerd` started with `--iptables=false --ip-forward=false --ip-masq=false` for create containers only with `--network=host`.
- **`docker_internal_network`** *(type=string, default="")* - Additional Docker network with resolving containers by name (resolving no available in default `bridge`). Only if `docker_network_manage: true`.

- **`docker_registry_mirrors`** *(type=list, default=[])* - Docker registry mirrors adding in `/etc/docker/daemon.json`.
- **`docker_registry_credentials`** *(type=list, default=[])* - List of objects with struct `{registry: "", username: "", password: ""}`. See [examples](#examples).

- **`docker_daemon_force_restart`** *(type=bool, default=false)* - Force restart `dockerd` when any containers is running.


### Examples
```yaml
# debian global
docker_apt_repository:
  repo_url: https://download.docker.com/linux/debian
  key_url: https://download.docker.com/linux/debian/gpg

# ubuntu global
docker_apt_repository:
  repo_url: https://download.docker.com/linux/ubuntu
  key_url: https://download.docker.com/linux/ubuntu/gpg

docker_registry_credentials:
  - registry: https://index.docker.io/v1/
    username: DOCKERHUB_USERNAME
    password: DOCKERHUB_PASSWORD

docker_internal_network: internal
```
