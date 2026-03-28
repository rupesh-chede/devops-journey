# 3-Tier Docker Application

## Architecture
- Frontend: Nginx (port 80)
- Backend: Python HTTP server (port 8080)
- Database: MySQL 8 with persistent volume

## How to run
```bash
docker-compose up -d
```

## Concepts covered
- Custom Dockerfile
- Docker volumes for data persistence
- Docker networking (custom bridge network)
- Docker Compose for multi-container orchestration
