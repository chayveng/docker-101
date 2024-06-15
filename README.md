# Fast API 101

## Start Up
```bash
# Create venv libralies
python venv .venv
pip install

# Linux
source .venv/bin/activate

# Windows
.\.venv\Scripts\activate

# Start FatpiApi
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

## Start Up with Docker

```bash
# Build image file
docker build -t fastapi_101 .

# Run Docker container
docker run -d -p 8000:8000 -v .:/app fastapi_101

# Run Docker container with Docker compose
docker compose up --build # Build and run
docker compose up # Run only


# Container Manage
docker ps
docker ps -a
dokcer stop <IMAGE_ID>
dokcer start <IMAGE_ID>
dokcer restart <IMAGE_ID>
# Logs follow up
docker logs -f --tail 100 fastapi_101
# Access Docker Container
docker exec -it fastapi_101 bash


# Images Manage
# REPOSITORY  TAG     IMAGE ID      CREATED         SIZE
# fastapiex   latest  ff0edcae07bb  17 minutes ago  195MB
docker images
dokcer rmi <IMAGE_ID>
dokcer rmi <IMAGE_ID>
docker tag <OLD_IMAGE_NAME>:<OLD_TAG> <NEW_IMAGE_NAME>:<NEW_TAG>

# Export image
docker save -o myapp_latest.tar myapp:latest
docker load -i myapp_latest.tar
```