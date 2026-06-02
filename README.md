# Flask App with Docker

This is a simple Flask application that prints **"Hello, World!"** in the browser.

## Application Overview

- Framework: Flask (Python)
- Default port: `5000`
- Endpoint: `/`
- Response: `Hello, World!`

## 🚀 Run the application with Docker

### 1. Build the Docker image
docker build -t neaimash/flask-app:v1 .
### 2. Run the container:
docker run -p 5000:5000 neaimash/flask-app:v1
### 3. Run the container: with volume:
docker run -p 5000:5000 -v .:/app neaimash/flask-app:v1

### Build and run with docker-compose:
docker-compose up --build

### Access the application:
http://localhost:5000
