## Publishing Docker Images to Docker Hub

Publishing my project 1 (**nextjs** & **fastapi**) docker images to Docker Hub.

![dockerhub](https://media.geeksforgeeks.org/wp-content/uploads/20230419170724/Docker-hub-registry.webp)

---

## Step 1: Created a Docker Hub Account

## Step 2: Login to Docker Hub from Terminal

run this command on terminal:

```bash
docker login
```

---

## Step 3: Building Docker Images with Proper Tags
***(open docker desktop on background)***<br>
Docker Hub images must be tagged in the format:

- **`<your-dockerhub-username>/<image-name>:<tag>`**

For the Next.js project:

```bash
docker build -t <your-dockerhub-username>/nextjs-docker:latest .
```

For the FastAPI project:

```bash
docker build -t <your-dockerhub-username>/fastapi-docker:latest .
```

***⚠️ Replace <your-username> with your actual Docker Hub username!***

---

## Step 4: Push Images to Docker Hub

```bash
# Next.js
docker push <your-dockerhub-username>/nextjs-docker:latest

# FastAPI
docker push <your-dockerhub-username>/fastapi-docker:latest
```

---

## Step 5: Verify on Docker Hub

- Go to https://hub.docker.com
- Navigate to your repositories by clicking on **My Profile** in the top right corner.
- You should see both *fastapi-docker* and *nextjs-docker* listed!

---

## Step 6: Pull & Run Your Images

Pull the images from Docker Hub:

```bash
# Next.js
docker pull <your-dockerhub-username>/nextjs-docker:latest

# FastAPI
docker pull <your-dockerhub-username>/fastapi-docker:latest
```

Run the images as docker containers:

```bash
# Next.js
docker run -d -p 3000:3000 --name my-nextjs-docker <your-dockerhub-username>/nextjs-docker:latest

# FastAPI
docker run -d -p 8000:8000 --name my-fastapi-docker <your-dockerhub-username>/fastapi-docker:latest
```

---
