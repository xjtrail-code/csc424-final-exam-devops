# CSC424 Final Exam DevOps Project



## Project Overview



This project modernizes the deployment process for a React + Vite frontend and a .NET backend API using Docker, Nginx, Docker Compose, and GitHub Actions.



The application is containerized and deployed through a CI/CD pipeline instead of being deployed manually.



---



# DevOps Setup



## Services



### Frontend

The frontend service is a React + Vite application. It is built using a multi-stage Docker build. The application is compiled using Node.js and then served using Nginx.



### Backend

The backend service is a .NET API. It uses a multi-stage Docker build where the SDK image is used for building the application and the ASP.NET runtime image is used for running the application.



### Nginx Reverse Proxy

Nginx acts as the reverse proxy for the application.



- Requests to `/` are routed to the frontend container.

- Requests to `/api/` are routed to the backend container.



Only the Nginx container exposes a public port to the host machine.



---



## Running the Application Locally



Run the following command from the root of the repository:



```bash

docker compose up --build -d
