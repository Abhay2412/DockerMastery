# Docker Install and Config
- Containers are fundamentals in the toolkit 
- "docker version" Checks if docker is works and returns information about client and server. On a new system to verify cli can confirm talk to engine 
- "docker info" Shows most config values for the engine 
- "docker" A list of some commands not all of them are present here
- "docker container run" New way to run these commands (docker command sub-command) 
- OLD: "docker run"(docker command)

# Start a Nginx Web Server
- An image is like source code, binaries, libraries we want to run
- A container is an instance of that image as a process 
- Can have many containers
- "docker container run --publish 80:80 nginx": It downloaded image nginx from Docker Hub, and then starts a new container from that image, opens a port 80 on the host IP, automatic forwarding traffic to the IP port 80.
- "docker container run --publish 80:80 --detach nginx"
- "docker container ls": Shows all of the containers which are running
- "docker container stop containerID": A specific container will be stopped the ID needs to be unique enough if many containers running 
- "docker container ls -a": Shows all of them which are stopped. 
- "docker container run --publish 80:80 --detach --name webhost nginx": Specified the name in this command of the container to be webhost 
- "docker container logs webhost": Shows all of the logs from the browser like GET requests 
- "docker container top webhost": Process running inside the container 
- "docker container --help": See all of the commands which we can run on this specific container 
- "docker container rm CID1 CID2 CID3": Can pass multiple container IDs to remove 
- "docker container rm -f CID": Remove forcefully a running container 

# What Happens When We Run a Container
- "docker container run": Looks for the image locally in the cache, doesn't find anything. Then looks in the remote image repo(Docker Hub). Downloads the latest version by default. Creates a new container based on that image. Gives it a virtual IP on a private network inside the docker engine. Opens up port 80 and automatically forward to port 80 in the container. 

# Container vs VM
- Containers are usually compared to virtual machines some similarities. Containers aren't mini VMs
- They are just processes and limited to what resources they can access 
- "docker run --name mongo -d mongo": Creates a container with mongo database
- "docker top" Shows the processes in the container 
  
# Assignment: Manage Multiple Containers
- docs.docker.com and --help are really helpful
- Three container application: Run a nginx, a mysql, and a httpd(apache server)
- Run all of them --detach(or -d), name them with --name
- nginx should listen on 80:80, httpd on 8080:80, mysql on 3306:3306
- When running mysql, use the --env(or -e) to pass in MYSQL_RANDOM_ROOT_PASSWORD=yes
- Use "docker container logs" on mysql to find the random password it created on startup
- Clean it all up with "docker container stop" and "docker container rm"
- Use "docker container ls" to ensure everything is correct 
- Commands used:
- "docker container run --publish 80:80 --detach --name webhost nginx"
- "docker container run --publish 80:80 -e MYSQL_RANDOM_ROOT_PASSWORD=yes -d --name database mysql"
- "docker container run --publish 8080doc:80 -d --name apache httpd"
  
# What's Going on In Containers:
- "docker container top" A process list in one container
- "docker container inspect" Details of one container config returns a JSON array
- "docker container stats" Performance stats of all the containers

# Getting a Shell Inside Containers:
- "docker container run -it" Start new container interactively (i[interactive]&t[pseudo] are different) 
- "docker container exec -it" Run additional command in existing container
- Helpful when you want to quickly tweak something 
- Alpine Linux distro is smaller than Ubuntu and does not have bash but can use the package manager for Alpine to install bash

# Docker Networks: Concepts
- Each container connects to a private virtual network
- Each virtual network routes through NAT firewall
- All containers on virtual network can talk to each other without opening their ports
- Best practice is to create a new virtual network for each app
- Attach containers to more then one virtual network or no network
- Skip virtual networks and use host IP(--net=host)
- By default the container is not using the host IP
- "docker container inspect --format" To get something specific from the config file

# Docker Networks: CLI
- "docker network ls" Shows the networks
- "docker network inspect" Inspect a network
- "docker network create --driver" Create a network 
- "docker network connect" Attach a network to the container
- "docker network disconnect" Detach a network from the container

# Docker Networks: DNS 
- "--link" Enable DNS on default bridge network
- Forget IP's cannot rely on them since they might change and the containers will fail
- Docker DNS uses the container names to talk with each other
- Can ping both of the containers in built feature

# Assignment: Using Containers for CLI Testing
- Use different Linux distro containers to check curl cli tool version 
- Use two different terminal windows to start bash in both centos:7 and ubuntu:14.04, using -it
- Use "docker container --rm"
- Ensure curl is installed and on latest version for that distro 
- curl --version