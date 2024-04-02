# Day-02
## STEP-1
```bash
 docker network create --driver bridge mongo-network
```
## STEP-2
```bash
docker run -d \
    -e MONGO_INITDB_ROOT_USERNAME="admin" \
    -e MONGO_INITDB_ROOT_PASSWORD="password" \
    -p 27017:27017 \
    --network mongo-network \
    --name mongo \
    mongo
```
## STEP-3
```bash
docker run -d \
    --network mongo-network \
    --name mongo-express \
    -p 8081:8081 \
    -e ME_CONFIG_MONGODB_ADMINUSERNAME="admin" \
    -e ME_CONFIG_MONGODB_ADMINPASSWORD="password" \
    -e ME_CONFIG_MONGODB_SERVER="mongo" \
    mongo-express
```
