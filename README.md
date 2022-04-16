# Ansible Role: Docker-offline. 

An Ansible Role that installs [Docker](https://www.docker.com) on Linux. No internet required

## Requirements

This role developed and tested with following Ansible versions:
| Name                                                   | Version         |
|--------------------------------------------------------|-----------------|
| [ansible](https://pypi.org/project/ansible-base/)      | ```>= 2.9.13``` |
| [ansible-base](https://pypi.org/project/ansible-base/) | ```>= 2.10.1``` |
| [ansible-core](https://pypi.org/project/ansible-core/) | ```>= 2.11.2``` |

Other Ansible versions was not tested but will probably work.

## Platforms

| Name   | Version             |
|--------|---------------------|
| Debian | ```buster```        |
| Ubuntu | ```focal, groovy``` |
| CentOS | ```7.4+, 8```       |
| RedHat | ```7.4+, 8```       |
| openSUSE | ```15.3 ```       |

Should work on most distributions that use Systemd, if you get a problem, feel free to open an issue

## Installation

Use `ansible-galaxy install ozarklake.docker-offline
` to install the latest stable release of role.

## Dependencies

None

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

```yaml
# Systemd options.
docker_service_state: started
docker_service_enabled: true

# Filename of the Docker binary package
# You can download from https://download.docker.com/linux/static/stable/
# example: curl https://download.docker.com/linux/static/stable/x86_64/docker-20.10.9.tgz -o docker.tar.gz
docker_binary_name: docker.tar.gz

# Whether to install docker-compose
docker_install_compose: true

# docker-compose binary filename
# download from https://github.com/docker/compose/releases
docker_compose_binary_name: docker-compose 

# Docker daemon options as a dict
docker_daemon_options: {}

```

## Example Playbook

You need to download the [Docker binaries](https://download.docker.com/linux/static/stable/) in advance and put them in your working directory. Also. If you need to install [docker-compose](https://github.com/docker/compose/releases). 

```yaml
- hosts: all
  roles:
    - ozarklake.docker-offline
```

## License

MIT