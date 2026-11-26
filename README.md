# 🐳 Docker Learning Journey

## Overview

This repository documents my hands-on Docker learning journey as part of the CoderCo DevOps programme.

Throughout this module, I learnt how to build, manage, optimise and troubleshoot Docker containers.

## Projects

### 1. Flask Application

- Containerised a Python Flask application.
- Created and configured Dockerfiles.
- Built and managed Docker images.
- Implemented multi-stage builds to reduce image size.

#### Image Optimisation Results

| Image | Disk Usage |
|---|---:|
| Original | 660 MB |
| Multi-stage | 215 MB |

Achieved a 67.4% reduction in image disk usage, saving 445 MB.

### 2. Multi-Container Application

Built a multi-container application using Python Flask, Redis and Docker Compose.

Flask handles web requests, while Redis stores and increments the visit count.

#### Technologies Used

- Docker
- Docker Compose
- Python
- Flask
- Redis
- Git and GitHub

#### Application Routes

- `/` — Displays a welcome message.
- `/count` — Increments and displays the visit count stored in Redis.

#### How to Run

Navigate to the multi-container application directory:

    cd multi-container-app

Build and start the containers:

    docker compose up --build -d

Access the application:

- Welcome page: http://localhost:5005/
- Visit counter: http://localhost:5005/count

Stop the application:

    docker compose down

## Challenges and Solutions

I encountered a port conflict and an incorrect port mapping while running my multi-container application.

Incorrect configuration:

    ports:
      - "5005:5005"

Correct configuration:

    ports:
      - "5005:5000"

This helped me understand the difference between host ports and container ports.

I also used Docker logs and container status commands to investigate and resolve the issue.

## Docker Commands Learnt

| Command | Description |
|---|---|
| docker build | Build a Docker image |
| docker run | Run a container |
| docker ps | List running containers |
| docker ps -a | List all containers |
| docker images | List Docker images |
| docker logs | View container logs |
| docker compose up | Start multiple services |
| docker compose down | Stop and remove services |
| docker compose ps | Check service status |
| docker compose logs | View service logs |
| docker compose exec | Execute commands inside a running service |
| docker volume ls | List Docker volumes |

## Key Takeaways

- Containerisation and image optimisation.
- Docker layer caching.
- Container networking and service discovery.
- Managing multiple containers with Docker Compose.
- Troubleshooting Docker and application issues.
- Understanding host and container port mappings.

## Future Improvements

- Persistent Redis storage using Docker volumes.
- Environment variables for application configuration.
- Scaling Flask containers.
- Implementing load balancing.

## Acknowledgements

Thank you to CoderCo for providing practical challenges and supporting my DevOps learning journey.