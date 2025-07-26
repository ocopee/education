# 🐳 Docker Compose - All-in-One Cheat Sheet

## 1. 🚀 What is Docker Compose?

Docker Compose is a tool for **defining and running multi-container Docker applications** using a **single YAML file** (`docker-compose.yml`).

### ✅ Main Benefits:

- Organize and launch services (web, db, cache...) easily.
- Automate the build/run/link process for containers.
- Great for development, testing, and CI/CD workflows.

---

## 2. 🧱 Structure of `docker-compose.yml`

```yaml
version: "3.8" # Compose file format version
services: # Group of containers
  app: # Service name
    image: myapp # Docker image to run
    build: . # Or build from Dockerfile in current dir
    ports:
      - "8080:80" # Port mapping (host:container)
    volumes:
      - ./app:/app # Mount host directory into container
    environment: # Environment variables
      - NODE_ENV=production
    depends_on: # Wait for other services to be ready
      - db

  db:
    image: postgres
    environment:
      - POSTGRES_USER=admin
      - POSTGRES_PASSWORD=secret
```
