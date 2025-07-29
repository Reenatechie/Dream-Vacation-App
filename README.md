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
