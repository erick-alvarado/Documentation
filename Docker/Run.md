# _Docker Run_
When an operator executes docker run, the container process that runs is isolated in that it has its own file system, its own networking, and its own isolated process tree separate from the host.
<p>&nbsp;</p>

## _Usage_ 
Use `-d` to run a container in the background.
```sh
 $ docker container run -d [docker_image]
```

Use `-it` to run the container interactively, you can access a command prompt inside the running container. 
```sh
 $ docker container run -it [docker_image] /bin/bash
```
Use `-p` to set specific ports for the host and the container. 
```sh
 $ docker container run -p [host_port]:[container_port] 
```
Use `-v` to have persistent data, shared between the host and the container.
```sh
 $ docker container run -v [/host/volume/location]:[/container/storage] [docker_image]
```

Use `cp` to copy a file from a container to the host
```sh
$ docker cp [containerId]:/file/path/within/container /host/path/target
```

<p>&nbsp;</p>



## _Reference_
- [Docker Run](https://phoenixnap.com/kb/docker-run-command-with-examples)
- [Docker Copy](https://stackoverflow.com/questions/22049212/docker-copying-files-from-docker-container-to-host)
