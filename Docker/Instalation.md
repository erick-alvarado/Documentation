# _Windows_
Your windows machine must meet some requirements to successfully install Docker Desktop. The following installation is targeted to work with Windows 10-64bit Home or pro 2004.

## _Steps_ 
1. Ensure the Hyper-V Windows option is active by pressing the Windows key and search for "Turn Windows features on or off". Select the Windows Hypervisor Platform and Virtual Machine Platform options. 

2. Get the installer from this [link](https://hub.docker.com/editions/community/docker-ce-desktop-windows), it includes Docker Engine, Docker CLI client, Docker Compose, Docker Content Trust, Kubernetes and Credential Helper.

3. Install required windows components for WSL 2. 

<p>&nbsp;</p>



# _Linux_
Run the following commands in console.
```sh
 $ sudo apt-get update
 $ sudo apt-get install docker-ce docker-ce-cli containerd.io
```
## _Reference_
- [Windows](https://docs.docker.com/desktop/windows/install/)
- [Linux](https://nodejs.org/)
