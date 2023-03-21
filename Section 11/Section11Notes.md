# Docker Hub
- An image registry is required it can be private or public but is needed for the container
- Build your own Docker registry as private image store
- Most popular public image registry
- Can build images on the fly 
- Link GitHub to Docker Hub, Create Automated Build based on your code commits from GitHub repo

# Docker Registry 
- A registry to store images for your network
- Not as full featured as the Docker Hub
- Useful in small teams 
- A registry starts to eat up disk space and hence garbage collection keeps the storage in check 

# Private Docker Registry
- An HTTPS server and runs on port 5000
- Re-tag existing images and push to your new registry 
- Docker does not talk to the registry without proper TLS 
- Need to create your own certificate for the registry
- Any other registry other than the Docker Hub the tag needs to have the host in it 

# Using Registry With Swarm
- Same as the localhost
- Swarm can talk to itself for the registry
- All the nodes can talk to the registry due to the Routing Mesh
- Play Docker lets you create the managers easily 