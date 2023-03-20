# Using Secrets With Local Docker Compose
- Can use the same compose file, and environment variables 
- "docker compose exec": Compose is not secure but does work and binds mount at runtime
- Does it in the background, a way around and to develop in like production but locally
- Match the production environment as close in the locally
- File based secrets only 

# Full App Lifecycle
- "docker compose up": for local development 
- An override file by default docker-compose.override.yml will use this by default
- Override any settings in the docker-compose.yml file
- Local development have to use the file based secrets
- "docker compose -f": The base file goes first and then the second file with the -d flag

# Service Updates
- Swarm updates provides rolling by one at a time with the settings you put in the update command 
- Limits downtime 
- Many options to control the update
- -add/-rm will usually have them 
- Scaling and rollback having their own commands
- "docker service rollback web"
- "docker service scale web=4"
- "docker service rm web"

# Healthchecks in Dockerfiles
- Supported in Dockerfile, Compose YAML, docker run and Swarm Services 
- Works right away and running inside the container 
- Simple execution and expects exit 0(OK) or exit 1(Error)
- Three states only -> starting, healthy, unhealthy
- Healthcheck status shows up in docker container ls