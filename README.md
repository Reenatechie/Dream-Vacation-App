### Dream Vacation Destinations APP
This project features a full-stack app where users can list countries they’d like to visit, with details for each. It uses a React frontend, Node.js backend, and PostgreSQL database—all containerized with Docker and orchestrated using Docker Compose


## Setup
1. Install Docker and Docker Compose.
2. Clone the repo: git clone <repository-url> and cd dream-vacation-destinations
3. Create .env file:
4. Run: docker-compose up --build
5. Open: http://localhost:{port}

## Project Overview
Frontend and backend code are sourced from the [Dream-Vacation-App] (https://github.com/obusorezekiel/Dream-Vacation-App). Users can view country details—such as capital, population, and region—and remove countries from their list. The project is production-ready, built with scalability, maintainability, and industry-standard CI/CD practices in mind.

## 🛠️ Running the Project
1. Clone the Repo
```bash
   git clone https://github.com/Reenatechie/Dream-Vacation-App
   cd Dream-Vacation-App

 2. Create a .env file at the root:
    <img width="675" height="380" alt="Screenshot 2025-07-29 at 10 32 25" src="https://github.com/user-attachments/assets/2dd0c49b-83ad-4bb0-80de-8b01c4f1a3d8" />
```

### 3. Start the application

```bash
docker-compose up --build
```

* Frontend: [http://localhost:3000](http://localhost:3000)
* Backend: [http://localhost:3001](http://localhost:3001)
* PostgreSQL: localhost:5432

---

### Docker Images pushed

* **Frontend**: `docker.io/theglobalreena/dream-vacation-frontend`
* **Backend**: `docker.io/theglobalreena/dream-vacation-backend`

---


### Features
1. Optimized multi-stage Docker builds to streamline the frontend deployment

2. Modular service architecture for better separation of concerns

3. Environment configuration managed via a .env file at the project root

4. Ready for both local and production Docker environments

5. Persistent database storage using Docker volumes for PostgreSQL



### Screenshot of Docker Hub Pushed Images In My Repositories

## Backend

<img width="1431" height="672" alt="Screenshot 2025-07-29 at 11 48 51" src="https://github.com/user-attachments/assets/548aaa62-f70f-4c0d-b6b9-fa01c11d1cac" />

## Frontend

<img width="1431" height="672" alt="Screenshot 2025-07-29 at 11 57 05" src="https://github.com/user-attachments/assets/14872d2b-a86e-4429-a9c7-53d2cb566780" />

## Both Frontend and Backend repository

<img width="1431" height="672" alt="Screenshot 2025-07-29 at 11 59 41" src="https://github.com/user-attachments/assets/e99cd42b-964e-417c-91e9-0044618aba24" />


## Screenshot of running app destination

<img width="1431" height="672" alt="Screenshot 2025-07-29 at 11 43 37" src="https://github.com/user-attachments/assets/0a0cffe3-37b4-4fe2-9d9d-d2cec7c6c063" />

---

## CI/CD with GitHub Actions
This project sets up an automated CI/CD workflow with GitHub Actions to build Docker images and publish them to Docker Hub.

### Workflow Configuration
The CI/CD pipeline is set up on the `github-actions`  branch, with distinct workflows handling the frontend and backend separately.

#### Frontend Workflow (`.github/workflows/frontend.yml`)
  - **Triggers**: Trigger a push to the `github-actions`  branch whenever changes are made in the frontend/ directory.
  - **Actions**:
     - Builds Docker image from `frontend/Dockerfile`
     - Pushes to Docker Hub as `theglobalreena/dream-frontend`
     - Creates automated tags derived from the branch name and commit SHA.
     - Leverages Docker layer caching to speed up the build process.

#### Backend Workflow (`.github/workflows/backend.yml`)
  - **Triggers**: Trigger a push to the `github-actions`  branch whenever changes are made in the backend/ directory.
  -  **Actions**:
     - Builds Docker image from `backend/Dockerfile`
     - Pushes to Docker Hub as `theglobalreena/dream-backend`
     - Performs automated tagging along with metadata extraction.


### GitHub Actions Features
 - **Path-specific triggers**: Workflows execute only when matching files are updated
 - **Docker Hub integration**: Automatically builds and pushes Docker images
 - **Secure secrets handling**: Stores Docker credentials in GitHub Secrets
 - **Build caching**: Uses Docker layer caching to enhance build speed
 - **Cross-platform compatibility**: Supports both arm64 and amd64 architectures
 - **Manual run option**: `workflow_dispatch` enables on-demand execution

### Setting up CI/CD
 1. **Fork this repository**
2. **Add Docker Hub secrets** in repository settings:
   - `DOCKER_USERNAME`: Your Docker Hub username
   - `DOCKER_TOKEN`: Your Docker Hub access token
3. **Push changes** to the `github-actions` branch
4. **Watch workflows** run automatically in the Actions tab

---

## Deployed Docker images
* **Frontend**: `docker.io/theglobalreena/dream-frontend`
* **Backend**: `docker.io/theglobalreena/dream-backend`
 

---

## Features
* **Optimized frontend builds** using multi-stage Docker builds
* **Separate services** to maintain clear responsibility boundaries
* **Environment configuration** managed via a root-level `.env` file
* **Compatible with both local and production** Docker deployments
* **Persistent PostgreSQL storage** through Docker volumes
* **Automated CI/CD workflows** powered by GitHub Actions
* **Seamless deployment integration** with Docker Hub


## Docker images pushed to my Docker Hub repositories

##Frontend
<img width="1431" height="830" alt="Screenshot 2025-08-13 at 00 33 48" src="https://github.com/user-attachments/assets/fcff3520-3461-46c1-b06b-98ca35af0032" />

##Backend
<img width="1431" height="830" alt="Screenshot 2025-08-13 at 00 35 06" src="https://github.com/user-attachments/assets/3120659c-6afc-4c81-8edb-758f4454b57f" />

## Github Actions After Build is Complete
<img width="1431" height="830" alt="Screenshot 2025-08-13 at 00 33 48" src="https://github.com/user-attachments/assets/6c0bce13-be9c-4a11-8a09-39be71a8548f" />



---
## Dream Vacation App Deployment on AWS

This project demonstrates deploying the Dream Vacation App into an AWS EC2 instance using a custom VPC, proper networking setup, and an automated CI/CD pipeline.

## Project Overview

* **Infrastructure**: Set up via AWS Management Console (ClickOps).

* **Compute**: Ubuntu EC2 instance with Docker & Docker Compose.

* **CI/CD**: GitHub Actions pipeline builds and pushes the app image to Docker Hub, then deploys to EC2.

* **App**: Dream Vacation App successfully accessible via EC2 Public IP.

## Part 1 – Networking Setup

1. **Custom VPC**

- Name: dream-vpc

- CIDR: 10.0.0.0/16

2. **Subnet**

- Name: dream-subnet

- CIDR: 10.0.1.0/24

3. **Internet Gateway**

- Name: dream-igw

- Route Table

4. **Name: dream-rt**

- Associated with dream-vpc

- Route configured to allow internet access via dream-igw.

## Screenshot of VPC


<img width="1440" height="854" alt="Screenshot 2025-09-02 at 14 01 29" src="https://github.com/user-attachments/assets/a7946f12-c5e5-4bb4-b617-014e39ed75cf" />


## Screenshot of Subnet

<img width="1440" height="854" alt="Screenshot 2025-09-02 at 14 01 44" src="https://github.com/user-attachments/assets/a3122d07-2e48-4ea6-a93a-24892e4036dd" />

## Screenshot of IGW

<img width="1440" height="854" alt="Screenshot 2025-09-02 at 14 02 02" src="https://github.com/user-attachments/assets/8e4fd3bb-421b-4e24-a739-e1179a85e296" />

## Screenshot of Route table
<img width="1440" height="854" alt="Screenshot 2025-09-02 at 14 01 53" src="https://github.com/user-attachments/assets/17782512-ad42-4165-bb6b-8b6b3db474bb" />

## Part 2 – EC2 Instance Setup

1. * **EC2 Instance**

- AMI: Ubuntu

- Type: t3.micro

- Security Group: Opened HTTP (80) and SSH (22).

2. * **User Data Script**

- Installed Docker & Docker Compose on startup.

## Screenshot of Running Instance

<img width="1440" height="854" alt="Screenshot 2025-09-02 at 14 00 59" src="https://github.com/user-attachments/assets/1fdd8505-bce5-4012-a648-0da14b85fba3" />

## Part 3 – CI/CD Deployment

1. * **CI/CD Pipeline**

- Builds app image and pushes to Docker Hub.

- Final stage SSHs into EC2, copies project files, pulls latest image, and runs docker-compose up -d.

## deploy pipleline
```bash
name: Build and Deploy App
on:
  push:
    branches:
      - EC2-deploy
jobs:
  changes:
    name: Detect Changes
    runs-on: ubuntu-latest
    outputs:
      backend: ${{ steps.filter.outputs.backend }}
      frontend: ${{ steps.filter.outputs.frontend }}
    steps:
      - uses: actions/checkout@v4
      - uses: dorny/paths-filter@v3
        id: filter
        with:
          filters: |
            backend:
              - 'backend/**'
              - 'docker-compose.yml'
            frontend:
              - 'frontend/**'
              - 'docker-compose.yml'
  build-backend:
    name: Build & Push Backend
    runs-on: ubuntu-latest
    needs: changes
    if: needs.changes.outputs.backend == 'true'
    steps:
      - uses: actions/checkout@v4
      - name: Login to DockerHub
        uses: docker/login-action@v2
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_TOKEN }}
      - name: Build and Push Backend Image
        run: |
          IMAGE=${{ secrets.DOCKER_USERNAME }}/dream-backend:${{ github.sha }}
          docker build -t $IMAGE ./backend
          docker push $IMAGE
          docker tag $IMAGE ${{ secrets.DOCKER_USERNAME }}/dream-backend:latest
          docker push ${{ secrets.DOCKER_USERNAME }}/dream-backend:latest
  build-frontend:
    name: Build & Push Frontend
    runs-on: ubuntu-latest
    needs: changes
    if: needs.changes.outputs.frontend == 'true'
    steps:
      - uses: actions/checkout@v4
      - name: Login to DockerHub
        uses: docker/login-action@v2
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_TOKEN }}
      - name: Build and Push Frontend Image
        run: |
          IMAGE=${{ secrets.DOCKER_USERNAME }}/dream-frontend:${{ github.sha }}
          docker build -t $IMAGE ./frontend
          docker push $IMAGE
          docker tag $IMAGE ${{ secrets.DOCKER_USERNAME }}/dream-frontend:latest
          docker push ${{ secrets.DOCKER_USERNAME }}/dream-frontend:latest
  deploy:
    name: Deploy to EC2
    runs-on: ubuntu-latest
    needs: [build-backend, build-frontend]
    steps:
      - uses: actions/checkout@v4
      - name: Copy docker-compose.yml to EC2
        uses: appleboy/scp-action@v0.1.7
        with:
          host: ${{ secrets.EC2_HOST }}
          username: ${{ secrets.EC2_USER }}
          key: ${{ secrets.EC2_KEY }}
          source: "docker-compose.yml"
          target: "/home/ubuntu/app/"
      - name: Deploy on EC2
        uses: appleboy/ssh-action@v1.0.3
        with:
          host: ${{ secrets.EC2_HOST }}
          username: ${{ secrets.EC2_USER }}
          key: ${{ secrets.EC2_KEY }}
          envs: BACKEND_IMAGE, FRONTEND_IMAGE, DOCKER_USERNAME, POSTGRES_USER, POSTGRES_PASSWORD, POSTGRES_DB, POSTGRES_PORT, REACT_APP_API_URL
          script: |
            set -e
            mkdir -p /home/ubuntu/app
            cd /home/ubuntu/app

            echo "Creating .env file"
            echo "BACKEND_IMAGE=${{ secrets.DOCKER_USERNAME }}/dream-backend:${{ github.sha }}" > .env
            echo "FRONTEND_IMAGE=${{ secrets.DOCKER_USERNAME }}/dream-frontend:${{ github.sha }}" >> .env
            echo "DOCKER_USERNAME=${{ secrets.DOCKER_USERNAME }}" >> .env
            echo "POSTGRES_USER=${{ secrets.POSTGRES_USER }}" >> .env
            echo "POSTGRES_PASSWORD=${{ secrets.POSTGRES_PASSWORD }}" >> .env
            echo "POSTGRES_DB=${{ secrets.POSTGRES_DB }}" >> .env
            echo "POSTGRES_PORT=5432" >> .env
            echo "REACT_APP_API_URL=${{ secrets.REACT_APP_API_URL }}" >> .env
            echo "COUNTRIES_API_BASE_URL=https://restcountries.com/v3.1" >> .env
            echo "POSTGRES_HOST=${{ secrets.POSTGRES_HOST }}" >> .env
            echo "DATABASE_URL=${{ secrets.DATABASE_URL }}" >> .env

            echo "Checking docker-compose.yml"
            ls -la
            cat docker-compose.yml
            if [ ! -f docker-compose.yml ]; then
              echo "Error: docker-compose.yml not found"
              exit 1
            fi

            echo "Logging into DockerHub"
            echo "${{ secrets.DOCKER_TOKEN }}" | docker login -u "${{ secrets.DOCKER_USERNAME }}" --password-stdin

            echo "Pulling backend and frontend images..."
            docker pull $(grep BACKEND_IMAGE .env | cut -d'=' -f2)
            docker pull $(grep FRONTEND_IMAGE .env | cut -d'=' -f2)

            echo "Starting containers with docker-compose..."
            docker-compose --env-file .env up -d --remove-orphans --force-recreate
```

## 2.  Testing Deployment

- Accessed the app via EC2 Public IP → Dream Vacation App running successfully.

## Screenshot of Github action pipeline

<img width="1440" height="854" alt="Screenshot 2025-09-02 at 14 00 41" src="https://github.com/user-attachments/assets/f44a10f6-4206-4ff0-8b64-3e79343b6b8e" />

## Screenshot of Frontend preview

<img width="982" height="685" alt="Screenshot 2025-09-02 at 14 00 00" src="https://github.com/user-attachments/assets/e5c55569-1062-4bfe-9690-6f5e960b781b" />

## Screenshot of backend preview


<img width="982" height="685" alt="Screenshot 2025-09-02 at 13 59 47" src="https://github.com/user-attachments/assets/247d95b7-fe00-4168-9a28-24fde6b491cb" />

## Notes

- Deployment was done entirely through AWS Console (ClickOps) and GitHub Actions.

- Docker Compose ensures easy container orchestration and reproducibility.

