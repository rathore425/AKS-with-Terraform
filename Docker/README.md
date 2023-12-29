# Docker
- Docker is a platform for developing, shipping, and running applications in containers. Containers are  lightweight, standalone, and executable packages that include everything needed to run a piece of software, including the code, runtime, libraries, and system tools. Docker provides a consistent environment across different stages of the development lifecycle, making it easy to deploy and scale applications.

Here's an interactive overview of Docker, covering its architecture, installation, and a simple example:

# Docker Flow
- Docker Client:
  - User issues commands through Docker CLI or GUI.
  - Commands sent to the Docker Daemon.
- Docker Daemon:
  - Background process managing Docker objects.
  - Handles container creation, networking, and volumes.
  - Interacts with the host OS kernel.
- Docker Registry:
  - Stores Docker images.
  - Default is Docker Hub, but private registries are common.
  - Docker Daemon pulls/pushes images.
- Docker Objects:
  - Containers, images, networks, volumes.
  - Managed by Docker Daemon.
  - Provides isolation, security, and resource management.
The flow involves the client issuing commands, Docker Daemon managing objects, interacting with Docker Registry for image storage, and orchestrating containerized applications.

# Docker Installation
- Linux:
```t
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
- Windows/Mac
Download and install Docker Desktop from the official Docker website.
https://docs.docker.com/get-docker/

# Running a Nginx Web Server in a Docker Container
- Pull the Nginx Image:
```t
docker pull nginx
```
- Run Nginx in a Container:
```t
docker run -d -p 8080:80 --name mynginx nginx
```
  - -d: Run the container in the background.
  - -p 8080:80: Map port 8080 on the host to port 80 on the container.
  - --name mynginx: Assign a name to the container.
- Access Nginx in a Web Browser:
Open a web browser and navigate to http://localhost:8080. You should see the default Nginx welcome page.
- Stop and Remove the Container:
```t
docker stop mynginx
docker rm mynginx
```

# Conclusion: 
- Docker simplifies the process of building, shipping, and running applications in a consistent and isolated environment. By using containers, developers can ensure that their applications run consistently across various environments, from development to production.