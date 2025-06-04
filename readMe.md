# Redis Docker Setup (Custom Port with Volume)

This project sets up a Redis server using Docker Compose.

---

## 🐳 Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

---

## 🚀 Getting Started

### 1. Clone the project

```yaml
git clone https://github.com/snlt11/redis-server-docker.git
```

### 2. Start Redis

```bash
docker-compose up -d
```

This starts Redis in detached mode and maps:
- Host port `6380` → Container port `6379`

### 3. Stop Redis

```bash
docker-compose stop
```

Or stop and remove the container (but keep the volume):

```bash
docker-compose down
```

### 4. Check Redis Version

```bash
docker exec -it redis_custom redis-server --version
```

---

## 📦 Data Persistence

Redis data is stored in a Docker volume named `redis_data`, so data is retained even if the container is removed.

---

## 🔧 Connect to Redis

From your local machine (assuming Redis CLI is installed):

```bash
redis-cli -p 6380
```

Or from inside the container:

```bash
docker exec -it redis_custom redis-cli
```

---

## ✅ Notes

- Uses the **latest** Redis image from Docker Hub.
- Port `6380` is used to avoid conflict with other Redis servers.
- Data is persisted with a named Docker volume.

---

## 📄 License

MIT – use it freely!
