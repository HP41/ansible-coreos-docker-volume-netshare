# Ansible Role: coreos-docker-volume-netshare
[![Build Status](https://travis-ci.org/HP41/ansible-coreos-docker-volume-netshare.svg?branch=master)](https://travis-ci.org/HP41/ansible-coreos-docker-volume-netshare)


## This role installs docker-volume-netshare for CoreOS
* Downloads docker-volume-netshare to `/opt/bin` which is a standard location to place binaries as it's writable and in `PATH`.
* Currently downloads docker-volume-netshare v0.34 using URL: `https://github.com/ContainX/docker-volume-netshare/releases/download/v0.34/docker-volume-netshare_0.34_linux_amd64-bin`.

## Requirements 
* Ansible >= 2.1
* Guest machine: CoreOS

### Default Variables that can be overridden or used as-is when using this role:
* `docker_volume_netshare_download_url`: The docker-volume-netshare download URL - Default=`https://github.com/ContainX/docker-volume-netshare/releases/download/v0.34/docker-volume-netshare_0.34_linux_amd64-bin`
* `docker_volume_netshare_location`: The location to which docker-volume-netshare must be placed. Default=`/opt/bin`, this is a writeable folder and exists within CoreOS's `PATH`
* `docker_volume_netshare_filename`: The filename of the docker-volume-netshare binary - Default=`docker-volume-netshare`
* `docker_volume_netshare_location_mode`: The `chmod` mode for the **folder** location where docker-volume-netshare will be placed - Default=`0755`
* `docker_volume_netshare_file_mode`: The `chmod` mode for the docker-volume-netshare **file** - Default=`a+x`