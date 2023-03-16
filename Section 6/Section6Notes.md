# Container Lifetime & Presistent Data
- Containers are usually disposable, temporary 
- Don't change things once they are running, redeploy when making a change 
- Data volumes: A special location to store outside a containers union file system
- Bind mounts: Local file path to the container(won't know it's from the host)

# Data Volumes
- Volumes need manual cleaning, removing the container does not do this
- A running container gets an unique location in the host 
- "docker volume inspect VID": Can see the information about the volume and the mount if on Linux can go to the path
- Named volumes friendlier way to assign volumes to container by adding -v in the "docker container run" 
- "-v mysql-db:/var/lib/mysql" by adding this we can see the volume name 
- "docker volume create": Few cases when needed to make them, for driver options and adding labels for it 

# Bind Mounting
- Mapping of the host file or directory to a container 
- Pointing to the same file in just two locations
- Host files win over the container
- Cannot use in Dockerfile at runtime using container run
- Bind mounts start with two forward slashes on Windows and the drive location