# Ansible Role: coreos-docker-volume-netshare
[![Build Status](https://travis-ci.org/HP41/ansible-coreos-docker-volume-netshare.svg?branch=master)](https://travis-ci.org/HP41/ansible-coreos-docker-volume-netshare)

-------------------

**[DOCKER-VOLUME-NETSHARE](https://github.com/ContainX/docker-volume-netshare)**

-------------------

## This role installs docker-volume-netshare for CoreOS
* Downloads docker-volume-netshare to `/opt/bin` which is a standard location to place binaries as it's writable and in `PATH`.
* Currently downloads docker-volume-netshare v0.34 using URL: `https://github.com/ContainX/docker-volume-netshare/releases/download/v0.34/docker-volume-netshare_0.34_linux_amd64-bin`.

## Requirements 
* Ansible >= 2.1
* Guest machine: CoreOS
* Docker >= 1.9.0

### Default Variables that can be overridden or used as-is when using this role:
* `docker_volume_netshare_download_url`: The docker-volume-netshare download URL - Default=`https://github.com/ContainX/docker-volume-netshare/releases/download/v0.34/docker-volume-netshare_0.34_linux_amd64-bin`
* `docker_volume_netshare_location`: The location to which docker-volume-netshare must be placed. Default=`/opt/bin`, this is a writeable folder and exists within CoreOS's `PATH`
* `docker_volume_netshare_filename`: The filename of the docker-volume-netshare binary - Default=`docker-volume-netshare`
* `docker_volume_netshare_location_mode`: The `chmod` mode for the **folder** location where docker-volume-netshare will be placed - Default=`0755`
* `docker_volume_netshare_file_mode`: The `chmod` mode for the docker-volume-netshare **file** - Default=`a+x`
* `docker_volume_netshare_run_as_service`: Create `systemd` unit to run docker-volume-netshare as a service? - Default=`no`
* `docker_volume_netshare_service_file_location`: `systemd` location of .service files that the docker-volume-netshare service will be placed in - Default=`/etc/systemd/system` as per [CoreOS docs](https://coreos.com/os/docs/latest/getting-started-with-systemd.html).
* `docker_volume_netshare_type`: The plugin type to run in the backgrouond if you chose to do so - Default=`nfs`
* `docker_volume_netshare_params`: Any parameters or arguments to pass along to the plugin. Please check the [original docker-volume-netshare repo](https://github.com/ContainX/docker-volume-netshare) on how this can be useful - Default=``
* `docker_volume_netshare_types`: **List** of different plugin types, please refer to the [original docker-volume-netshare repo](https://github.com/ContainX/docker-volume-netshare) for more info - Default=`nfs, efs, cifs`
* `docker_volume_netshare_nfs_spec_file_location`: The location where to place nfs.spec file for NFS to work as expected, pelase refer to this [link](https://github.com/ContainX/docker-volume-netshare/issues?utf8=%E2%9C%93&q=nfs.spec) on why it might be needed. Override this with an empty value if it isn't needed - Default=`/etc/docker/plugins`