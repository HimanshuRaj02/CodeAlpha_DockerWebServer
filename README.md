
# Dockerized Web Server — CodeAlpha Task 4

## Overview
A responsive website served by Nginx inside a Docker container.
This project demonstrates Docker image creation, container deployment,
port mapping, logging, and basic container lifecycle management.

## Technologies
- HTML5
- CSS3
- Docker
- Nginx
- Ubuntu on WSL

## Project Structure
```text
codealpha-docker-webserver/
├── Dockerfile
├── index.html
├── style.css
└── README.md
```

## Build the Docker Image
```bash
sudo docker build -t codealpha-webserver:v1 .
```

## Run the Container
```bash
sudo docker run -d --name codealpha-web -p 8080:80 codealpha-webserver:v1
```

Open http://localhost:8080 in your browser.

## Container Management
```bash
sudo docker ps
sudo docker logs codealpha-web
sudo docker stop codealpha-web
sudo docker start codealpha-web
sudo docker inspect codealpha-web
```

## Learning Outcomes
- Built a Docker image using a Dockerfile.
- Served website files using Nginx.
- Mapped a host port to a container port.
- Practiced container lifecycle management and troubleshooting.

## Internship
CodeAlpha — Task 4: Web Server Using Docker
