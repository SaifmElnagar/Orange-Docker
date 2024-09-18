# Docker Tasks and Labs

Welcome to my repository showcasing the Docker tasks and labs I've completed. This repository includes various Docker configurations and examples that demonstrate my experience with Docker.

## Table of Contents

1. [Overview](#overview)
2. [Setup](#setup)
3. [Tasks and Labs](#tasks-and-labs)
   - [Lab 1](#lab-1)
     - [P1: Custom Nginx Docker Image](#p1-custom-nginx-docker-image)
     - [P2: React App Docker Container](#p2-react-app-docker-container)
     - [P3: Docker Network Types](#p3-docker-network-types)
     - [P4: Bridge Network Example](#p4-bridge-network-example)
4. [Usage](#usage)
5. [Contributing](#contributing)
6. [License](#license)

## Overview

This repository contains Docker configurations and examples for various tasks and labs. These tasks aim to enhance my understanding and practical skills in working with Docker containers and images.

## Setup

To get started with these Docker tasks, follow these steps:

1. **Install Docker**: Make sure you have Docker installed on your machine. You can download it from the [official Docker website](https://www.docker.com/products/docker-desktop).
2. **Start Docker**: Ensure that Docker is running on your system.

## Tasks and Labs

### Lab 1

#### P1: Custom Nginx Docker Image

In this task, I created a custom Nginx Docker image based on Ubuntu. The Dockerfile includes:

- Installation of Nginx
- Two `index.html` files: one as a file and another packed as a `.tar` archive in `/var/www/html`
- Exposing ports
- Starting Nginx
- Port mapping

**Dockerfile**: `Dockerfile-nginx`

#### P2: React App Docker Container

This task involves creating a Docker container for a React app using a single-stage build.

**Dockerfile**: `Dockerfile-react`

#### P3: Docker Network Types

This section covers various Docker network types and their definitions:

- **Bridge**: The default network driver. Containers connected to the bridge network can communicate with each other, but not with containers outside the bridge network unless explicitly exposed.
- **Host**: Removes network isolation between the container and the Docker host. Containers use the host's networking directly.
- **Overlay**: Creates a network that spans multiple Docker hosts, allowing containers on different hosts to communicate with each other.
- **Macvlan**: Assigns a MAC address to a container, making it appear as a physical network interface on the network.

#### P4: Bridge Network Example

In this task, I created a bridge network and ran two containers from the Ubuntu image with different names. The containers were able to ping each other using their names.

**Commands Used**:

```bash
docker network create my-bridge-network
docker run -d --name container1 --network my-bridge-network ubuntu sleep infinity
docker run -d --name container2 --network my-bridge-network ubuntu sleep infinity
docker exec container1 ping container2
```

## Usage

To apply the configurations or run the tasks, use the following commands:

1. **Build Docker Images**: `docker build -t <image-name> -f <Dockerfile> .`
2. **Run Docker Containers**: `docker run <options> <image-name>`

Replace `<image-name>` with the actual image name and `<Dockerfile>` with the appropriate Dockerfile name.

