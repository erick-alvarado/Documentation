# _DockerFile_
The docker build command builds an image from a `DockerFile`. A `DockerFile` es a text document that contains all the commands a user could call on the command line to assemble an image. 

Traditionally, the `DockerFile` is called `DockerFile` and located in the root of the context.

<p>&nbsp;</p>

## _Usage_ 
This example shows a build command that uses the current directory (`.`) as build context.

```sh
 $ docker build .
```
You can use the `-f` flag to point to a Dockerfile anywahere in your file system.
```sh
 $ docker build -f /path/to/a/Dockerfile .
```

You can specify a repository and a tag at which to save the new image if the build succeeds.
```sh
 $ docker build -t repository/tag .
```


To increase the builds performance, exclude files and directories by adding a `.dockerignore` file to the context directory. Here is an example. 

```sh
 # comment
 */temp*
 */*/temp*
 temp?
```
The previous file causes the following build behavior.
| Rule | Behavior |
| ------ | ------ |
| `# comment` | Ignored |
| `*/temp*` | Exclude files and directories whose names start with temp in any inmmediate subdirectory of the root. For example, the plain file `/somedir/temporary.txt` is excluded, as is the directory `/somedir/temp   `. |
| `*/*/temp**` | Excludes files and directories starting with `temp` from any subdirectory that is two levels below the root. For example, `/somedir/subdir/temporary.txt` is excluded |
| `temp?` | Exclude files and directories in the root directory whose names are a one-character extension of `temp` . For example, `/somedir/subdir/temporary.txt` is excluded. |

<p>&nbsp;</p>

## _Format_ 

The instruction is not case-sensitive. However, convention is for them to be UPPERCASE to distinguish them from arguments more easily. 
| Instruction | Behavior | Example |
| ------ | ------ | ------ |
| `FROM` | Specifies the valid docker image name. Its downloaded from docker hub if it does not exist locally | `FROM golang:latest`|
| `MAINTAINER` | Specifies the autor who creates this new dcker image for the support. | `MAINTAINER erickalv.bugs@hotmail.com`|
| `LABEL` | Specifies metadata informations to an image, it is a key-value pair. | `LABEL "Application_Environment"="Development"`|
| `EXPOSE` | Inform about the network ports that the container listens on runtime. | `EXPOSE 8080 `|
| `ADD` | Copy files, directories and remote URL files to the destination. It allows the `src` to be a URL, and extracts the file if its a compressed file. | `ADD src dest` |
| `COPY` | Copy files, directories and remote URL files to the destination.   | `COPY /src /dest` |
| `RUN` | Execute any commands on top of the current image and will create a new layer.  | `RUN apt-get update` |
| `CMD` | Set a command to be executed when running a container. It is overwwritenn by `docker run`. | `CMD python myapplication.py` |
| `ENTRYPOINT` | Configure and run a container as an executable. It is not overwritten by `docker run` . | `ENTRYPOINT python myapplication.py` |
| `VOLUME` | Create or mount a volumen to the docker container from the docker host filesystem. | `VOLUME /appdata:/appdata`| 
| `USER` | Set the username, group name, UID and GID for running subsequent commands. | `USER webadmin`|
| `WORKDIR` | Set the working directory. | `WORKDIR /app/` |
| `ENV` | Set environment variables with key and value. | `ENV name value`|

 

<p>&nbsp;</p>

## _Reference_
- [Dockerfile](https://docs.docker.com/engine/reference/builder/)
- [Instructions](https://www.learnitguide.net/2018/06/dockerfile-explained-with-examples.html)
