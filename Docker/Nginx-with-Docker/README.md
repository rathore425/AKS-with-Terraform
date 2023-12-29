# Create a new Docker Image, Run as Container and Push to Docker Hub

# Pre-requisite:
- Create your Docker Hub account at https://hub.docker.com/.

# Step 1: Run the base Nginx container
- Access the URL http://localhost
```t
docker run --name mynginx -p 80:80 -d nginx
docker ps
docker stop mynginx
```
# Step 2: Create Dockerfile and Copy Our Customized index.html
- Dockerfile is created with the correct content

# Step 3: Build Docker Image & run it
```t
docker build -t <your-docker-hub-id>/mynginx_image1:v1 .
docker run --name mynginx1 -p 80:80 -d <your-docker-hub-id>/mynginx_image1:v1
```

# Step 4: Tag & Push the Docker Image to Docker Hub
```t
docker tag <your-docker-hub-id>/mynginx_image1:v1 <your-docker-hub-id>/mynginx_image1:v1-release
docker push <your-docker-hub-id>/mynginx_image1:v1-release
```

# Step 5: Verify the Same on Docker Hub
- Login to Docker Hub and verify the image we have pushed.
URL: https://hub.docker.com/repositories