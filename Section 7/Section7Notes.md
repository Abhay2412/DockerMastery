# Docker Compose
- Containers are single processes rarely use them to provide solutions to the client
- 2 different but related things
- YAML a formatted file for containers, networks, volumes
- A CLI tool called docker-compose used for local development 
- docker-compose.yml easier to get around environment in your local machine
- First line is always the version if no version always assumed to be v1
- Can overwrite the default commands in this file as well 
- Helps with saving typing docker run commands 
  
# Basic Compose Commands
- Not ideal for production ideal for local development 
- "docker compose up": Starts all the volumes/networks/containers
- "docker compose down": Stop all containers and remove containers, volumes, networks
- Kind of a replacement of the docker cli but still talking to the API in the backend

# Adding Image Building to Compose Files
- Compose can help building the custom images
- Builds it only if cannot find in cache 
- "docker compose build" Rebuilding 