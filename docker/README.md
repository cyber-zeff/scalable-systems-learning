## Basic Docker Commands (for the future  me).

1. Check Version:
   ```bash
   docker --version

   # Check doker sys info
   docker info
   ```

2. Docker Image:
   ```bash
   # Build an Image
   docker build -t image_name .

   # List all Images (for verification)
   docker images

   # Remove an Image
   docker rmi image_id
   ```

3. Docker Containers:
   ```bash
   # Run a Container
   docker run image_name
   
   # Run with port mapping
   docker run -p 3000:3000 image_name
   
   # Run in detached mode
   docker run -d image_name
   
   # List Running Containers
   docker ps
   
   # List all containers (running + stopped)
   docker ps -a
   
   # Stop a Container
   docker stop container_id
   
   # Start a Stopped Container
   docker start container_id

   # Remove a Container
   docker rm container_id
   ```

4. Build & run:
   ```bash
   # Create docker image
   docker build -t fastapi-docker .

   # Verify
   docker images

   # Run docker container (ensure docker desktop is open)
   docker run -p 8000:8000 fastapi-docker
   ```

---