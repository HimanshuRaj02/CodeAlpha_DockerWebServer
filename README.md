# Dockerized Web Server with Nginx

A hands-on DevOps project built as part of my **CodeAlpha DevOps Internship** to practise Docker containerization and web server deployment.

## Project Overview

I built this project to understand how a static website can be packaged into a Docker image and served through an Nginx web server.

The project uses HTML and CSS for the website, Docker to package and run it in a container, and Nginx to serve the website over HTTP. A Docker health check is also configured to verify that the web server is responding.

## Project Screenshots

### 1. Website Homepage

![Dockerized Web Server Homepage](screenshots/homepage.png)

### 2. Website Features and Project Information

![Website Features and Project Information](screenshots/project-footer.png)

## Architecture

The request follows this path when the website is opened in a browser:

```mermaid
flowchart LR
    A[Web Browser] --> B[localhost:8080]
    B --> C[Docker Container]
    C --> D[Nginx Web Server]
    D --> E[index.html]
    D --> F[style.css]
```

## Features

- Custom Docker image based on `nginx:alpine`
- Static website served using Nginx
- Host-to-container port mapping (`8080:80`)
- Docker health check to verify web server availability
- Container status and log inspection
- Responsive website built with HTML and CSS
- Git and GitHub for version control and project sharing

## Technologies Used

- **Docker** — image building and container management
- **Nginx** — web server
- **Linux (Ubuntu on WSL)** — development environment
- **HTML5 and CSS3** — website structure and styling
- **Git and GitHub** — version control and source code hosting

## Project Structure

```text
codealpha-docker-webserver/
├── Dockerfile
├── index.html
├── style.css
├── README.md
└── screenshots/
    ├── homepage.png
    └── project-footer.png
```

## Run the Project Locally

### Prerequisites

- Docker installed and running
- Git installed
- A browser to access the website

### Step 1: Clone the repository

```bash
git clone https://github.com/HimanshuRaj02/CodeAlpha_DockerWebServer.git
cd CodeAlpha_DockerWebServer
```

### Step 2: Build the Docker image

```bash
sudo docker build -t codealpha-webserver:v2 .
```

### Step 3: Run the container

```bash
sudo docker run -d --name codealpha-web -p 8080:80 codealpha-webserver:v2
```

### Step 4: Open the website

Open the following address in your browser:

http://localhost:8080

### Step 5: Verify the container

Check the running container:

```bash
sudo docker ps
```

Check the health status:

```bash
sudo docker inspect --format='{{.State.Health.Status}}' codealpha-web
```

Check the server logs:

```bash
sudo docker logs codealpha-web
```

The health status should become `healthy` after the health check succeeds.

## Container Management

Stop the container:

```bash
sudo docker stop codealpha-web
```

Start the container again:

```bash
sudo docker start codealpha-web
```

Remove the container:

```bash
sudo docker rm -f codealpha-web
```

## What I Learned

Through this project, I practised:

- Writing a Dockerfile and building a Docker image
- Running a website inside a Docker container
- Serving static files through Nginx
- Mapping host ports to container ports
- Configuring and checking a Docker health check
- Inspecting container status and server logs
- Managing the container lifecycle
- Using Git and GitHub to maintain and share project files

## Internship Context

This project was developed as part of my **CodeAlpha DevOps Internship** to gain practical experience with Docker and Nginx.

## Author

**Himanshu Raj**
