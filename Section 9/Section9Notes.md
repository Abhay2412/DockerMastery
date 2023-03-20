# Scaling Out with Overlay Networking
- "--driver overlay" when creating a network 
- For container to container traffic 
- Each service can be connected to multiple networks

# Scaling Out with Routing Mesh
- Incoming packets for a Service to a proper Task
- Spans all nodes in Swarm 
- Listening on all nodes for traffic
- In the background it routes to a different node 
- Virtual IP is created for the service 
- A layer 3 load balancer which is at TCP

# Swarm Stacks
- Stacks accept compose files 
- "docker stack deploy": Helps with deploy this compose file
- Stacks manages all objects adds stack name to start of their name
- New deploy key in compose file
- Can have delay(warmup time) for containers

# Swarm Secrets
- Easiest secure solution for storing secrets, comes out of the box
- A secret(anything you don't want on a front page of the newspaper) is: Usernames, passwords, TLS certificates, SSH keys 
- It is stored on disk on the manager nodes 
- First put in Swarm and then assign them to the service
- Secrets depend on Swarm

# Using Secrets in Swarm Services
- "docker secret create": Storing the secrets in the hardware on the disk 
- And it spits out a ID 
- "Docker secret ls": Can see the list of the secrets 

# Using Secrets in Swarm Stacks
- Not keeping the secrets on the host and it defeats the purpose 
- Do not leave residual secrets which are easy to access 
