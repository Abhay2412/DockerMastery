# What's In An Image
- The application binaries and dependencies 
- Metadata about the image data and how to run the image
- Not a complete Os no kernel, the host provides the kernel and this is what makes different from a virtual machine
- Small as one file or can be a big as a Ubuntu distro with PHP, and other packages
  
# Docker Hub Registry Images
- Without the account name are the official ones 
- An official images and Docker Inc, take care of them tested, documented and obeying best practice
- Can specify the version of the image by using "docker pull nginx:version#"

# Images and Their Layers
- Image is not like a big blob and may have cached some parts of the image already
- "docker history image nginx": All the changes in the image and can see the size of the layers
- Each image will have different set of layers 
- Every layer gets its own SHA and is helpful to identify them 
- All containers in the images look like a stack of pancakes 
- COW(Copy on Write) store a copy of the base image in the container 
- "docker image inspect nginx": Gives you back the metadata, the basic info about image ID, and how it can be run which ports you need to open, environment variables which are passed in 

# Image Tagging and Pushing to Docker Hub
- Tags need to be in specific format in order for it to work on Docker Hub
- "docker image tag nginx username[on DockerHub]/nginx"
- "latest" for official means the current but not always true 
- "docker image push username/nginx": Pushes the repository on DockerHub
- "docker login": Prompts you to login for the username and password
- "docker logout": If on an untrusted device logout 
- If wanting to make a repository private create it first and set the visibility to be false 

# Dockerfile Basics
- A recipe for creating your own image 
- Seems to look like a shell script but is different 
- Default name is "Dockerfile"
- "FROM": is in every Docker file nowadays it will be alpine 
- "ENV": set environment variables really important in containers way to push key or values to them 
- Each stanza in the Dockerfile is it's own layer and the order matters from top to bottom 
- "RUN": install a package software, unzipping 
- "EXPOSE": By default no TCP or UDP ports are open until or unless we state them
- "CMD": Final command when a new container is launched from an image
  
# Running Docker Builds
- Shorter build times things that change the bottom at the top so it can use the cache and the things change the most at the bottom 

# Extending Official Image
- "WORKDIR": cd and change the directory 
- "COPY": Use a different file to point 
- Can inherit images from others in the dockerfile

# Assignment: Build Your Own Dockerfile
- Dockerfiles are part process workflow and part art
- Take existing Node.js app and Dockerize it
- Make Dockerfile. Build it. Test it. Push it. (rm it). Run it. 
- Iterative process 
- Use the Apline version of he official "node" 6.x image