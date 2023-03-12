# What is Docker in 2022?
- The Docker image, registry, container. Three of them go together(Build, ship, run) core principles in the cloud ecosystem. 
- CNCF(Cloud Native Computing Foundation)
- The Docker image: universal package manager, is cross OS and platform and runs on everything as it is running Linux or Windows
- Dockerfile requires FROM, RUN, WORKDIR, COPY, CMD(these are stanzas and in this file it is from top to down)
- "docker build" simple command and turn the dockerfile multiple images into one single image. 
- The Docker registry: universal app distribution, helps with moving container images. GitHub, Bitbucket, GitLab has their own. Has a unique SHA hash like the commit ID. 
- "docker push" and push them into a registry 
- "docker pull" An identical copy into another Machine 
- The Docker container: Identical runtime environments. Docker engine will run behind Linux/Windows download the images and verify them. 
- "docker run" this is running the application in it's container. 
  
# Quick Container Run
- Play with Docker online on the browser. 
- "docker version" Get information about the client and server(Socket, TCP/TLS, SSH Tunnel like Networking concepts)
- "docker run -d -p 8800:80 httpd" -d is for detach run in background, -p is open a port
- "docker ps" A list of all container process running. 

# Why Docker?
- Helps with Software Life Cycle. Three overall reasons (Isolations, Environments, and Speed)
- Containers exist because of better isolation in a single OS, differences between each environment(connections, ports, URLS may be different rest is same), increase speed of change(do everything faster)