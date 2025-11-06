# CTFd Docker Stack

This directory contains a Docker Compose setup for CTFd, Postgres, and Redis.

## Prerequisites
- Docker and Docker Compose

## Quickstart
1. Copy env template:
   
   ```bash
   cd infrastructure/ctfd-docker
   cp example.env .env
   ```
2. Start the stack:
   
   ```bash
   docker compose up -d
   ```
3. Open CTFd at `http://localhost:8000` and run the initial setup.

## Development with the React client
- The Vite dev server is configured to proxy `/api` to `http://localhost:8000`, so the client can call `"/api/v1/..."` without CORS issues.
- For production, place a reverse proxy in front (e.g., Nginx) or enable CORS at the backend.

## Volumes
- `ctfd-db` — Postgres data
- `ctfd-redis` — Redis data
- `ctfd-uploads` — CTFd uploads


