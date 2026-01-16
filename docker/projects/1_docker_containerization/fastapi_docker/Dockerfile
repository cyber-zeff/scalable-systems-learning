# Use official Python 3.12 slim image
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Copy all project files into container
COPY . .

# Install uv CLI
RUN pip install uv

# Install all project dependencies
RUN uv sync

# Expose port 8000 for FastAPI
EXPOSE 8000

# Command to run the FastAPI app
CMD ["uv", "run", "fastapi", "dev", "main.py", "--host", "0.0.0.0"]
