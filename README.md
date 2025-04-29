# Dockerized Flask Application

This is a simple Flask application that has been Dockerized for easy deployment and scalability. It includes a `Dockerfile`, `docker-compose.yml`, and a `.dockerignore` file to ensure a smooth experience in development, testing, and production environments.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Dockerizing the Flask App](#dockerizing-the-flask-app)
- [Using Docker Compose](#using-docker-compose)
- [Deployment](#deployment)
- [Optimizing the Docker Image](#optimizing-the-docker-image)
- [License](#license)

## Prerequisites

Before you can run this project, ensure you have the following installed:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/)
- [Git](https://git-scm.com/)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/flask-docker-app.git
   cd flask-docker-app

Dockerizing the Flask App
This Flask app is containerized using Docker to ensure a consistent and reproducible environment across various systems. The project includes the following files:

Dockerfile: The instructions to build the Docker image.

.dockerignore: Specifies which files to exclude from the Docker image (e.g., .git, __pycache__, etc.).

requirements.txt: Lists the dependencies for the Flask app.

Dockerfile Explanation
FROM python:3.9-slim: Starts with a lightweight Python image.

WORKDIR /app: Sets the working directory to /app inside the container.

COPY . /app: Copies all files into the /app directory inside the container.

RUN pip install --no-cache-dir -r requirements.txt: Installs dependencies from requirements.txt.

EXPOSE 5000: Exposes port 5000 to make the app accessible from outside the container.

CMD ["gunicorn", "-b", "0.0.0.0:5000", "app:app"]: Runs the app using gunicorn (a production-ready web server) on port 5000.