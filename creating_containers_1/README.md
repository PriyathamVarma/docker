# Creating containers

## Popular Commands

To check docker version 

``` docker - v ```

or, 

``` docker version ```

you will get 

```bash
Client:
 Cloud integration: v1.0.31
 Version:           20.10.23
 API version:       1.41
 Go version:        go1.18.10
 Git commit:        7155243
 Built:             Thu Jan 19 17:35:19 2023
 OS/Arch:           darwin/amd64
 Context:           default
 Experimental:      true

Server: Docker Desktop 4.17.0 (99724)
 Engine:
  Version:          20.10.23
  API version:      1.41 (minimum version 1.12)
  Go version:       go1.18.10
  Git commit:       6051f14
  Built:            Thu Jan 19 17:32:04 2023
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.6.18
  GitCommit:        2456e983eb9e37e47538f59ea18f2043c9a73640
 runc:
  Version:          1.1.4
  GitCommit:        v1.1.4-0-g5fd4c4d
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
```
<hr/>

You can use ``` docker info ```

to get more information 

```bash
Client:
 Context:    default
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc., v0.10.3)
  compose: Docker Compose (Docker Inc., v2.15.1)
  dev: Docker Dev Environments (Docker Inc., v0.1.0)
  extension: Manages Docker extensions (Docker Inc., v0.2.18)
  sbom: View the packaged-based Software Bill Of Materials (SBOM) for an image (Anchore Inc., 0.6.0)
  scan: Docker Scan (Docker Inc., v0.25.0)
  scout: Command line tool for Docker Scout (Docker Inc., v0.6.0)

Server:
 Containers: 0
  Running: 0
  Paused: 0
  Stopped: 0
 Images: 7
 Server Version: 20.10.23
 Storage Driver: overlay2
  Backing Filesystem: extfs
  Supports d_type: true
  Native Overlay Diff: true
  userxattr: false
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 io.containerd.runtime.v1.linux runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 2456e983eb9e37e47538f59ea18f2043c9a73640
 runc version: v1.1.4-0-g5fd4c4d
 init version: de40ad0
 Security Options:
  seccomp
   Profile: default
  cgroupns
 Kernel Version: 5.15.49-linuxkit
 Operating System: Docker Desktop
 OSType: linux
 Architecture: x86_64
 CPUs: 6
 Total Memory: 7.675GiB
 Name: docker-desktop
 ID: 3C5S:7457:PFPR:U7AP:GVUV:VFYU:IPFJ:WYLT:E4BW:SN3I:QBH4:NJF3
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http.docker.internal:3128
 HTTPS Proxy: http.docker.internal:3128
 No Proxy: hubproxy.docker.internal
 Registry: https://index.docker.io/v1/
 Labels:
 Experimental: false
 Insecure Registries:
  hubproxy.docker.internal:5000
  127.0.0.0/8
 Live Restore Enabled: false
```

<hr/>

To get all commands list 

``` docker ```

## Image vs Container

- An Image is the application that we want to RUN

- A Container is the Instance of the Image that is running as a process.

  ### Running NGINX server

1. ``` docker container run --publish 80:80 nginx ```

> This will download the latest version of NGINX.
> 
> Starts a new container because we used --publish.
> 
> Exposes to port 80.

1.1 Use ``` docker container run --publish 80:80 --detach nginx ```

This is for running multiple containers

2. ``` docker container ls ```

This will give you the list of containers running.

It looks like this,

```bash

CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                NAMES
e5871cac1c5e   nginx     "/docker-entrypoint.…"   8 seconds ago   Up 7 seconds   0.0.0.0:80->80/tcp   sharp_banzai

```

3. ``` docker container stop CONTAINER_ID<JUST FIRST THREE CHRACTERS> ```

This will stop the specific container
