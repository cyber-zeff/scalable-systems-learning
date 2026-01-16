## FastAPI Docker Project Working Steps

1. Create project:
   ```bash
   uv init fastapi-docker

   cd fastapi-docker
   
   uv add fastapi[standard]
   ```

2. Update `main.py`:
   ```python
   from fastapi import FastAPI

   app = FastAPI()

   @app.get("/")
   def read_root():
       return {"message": "Hello from FastAPI Docker!"}
   ```

3. Create `Dockerfile` in project root:
   ```dockerfile
   # Install python version 3.12
   FROM python:3.12-slim 
   
   # Set working directory means (where the commands will be executed)
   WORKDIR /app 
   
   # Copy all files to working directory
   COPY . . 
   
   # Install uv using pip
   RUN pip install uv 
   
   # Install all dependencies in a project
   RUN uv sync 
   
   # Application access port, localhost:8000 or 127.0.0.1:8000
   EXPOSE 8000 
   
   # Run the application
   CMD ["uv", "run", "fastapi", "dev", "main.py", "--host", "0.0.0.0"]
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