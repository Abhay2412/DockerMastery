# Swarm Mode
- Apps can run the same regardless of the deployment method 
- A clustering solution built inside Docker single manageable unit
- Not enabled immediately have to do it manually 
- Manager nodes have a local database stores their configuration and ensure they can manage swarm nodes
- Managers can also be workers vice versa as well 
- "docker run" can only deploy one container but didn't scale up 
- A single service can have multiple tasks which can launch containers 
- "docker swarm init": To enable it and a lot of security information is generated 
- Can only be 1 leader among the managers "docker node ls": Can promote/demote them from using this command 
- "docker service": Replaces the docker run command and it's focus was only a single host, but this command is for cluster of nodes 
- 1/1: Number on the left is how many are actual running and on the right how many you have specified to run. And always tries to keep these numbers the same
- "docker service update": Allowed us to update the container without stopping and killing it 