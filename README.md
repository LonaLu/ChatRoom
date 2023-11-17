# Nimble Challenge - Chat Application


## Local Deployment Guide
### Client
Modify the .env file as needed, then run following commands to start client at localhost:3000
```
cd public 
yarn
yarn start
```

### Server
Update the MongoDB URL variable in the .env file to match the MongoDB database in use, then run following commands to start server at localhost:5000
```
cd server
yarn
yarn start
```
Please note that after the initial deployment, there is no need to run the yarn command again; you can directly execute yarn start.

## Docker
To build docker images, navigate to corresponding directory and run following commands
### Client
```
docker build -t client .
```
### Server
```
docker build -t server .
```
### To run docker images
```
docker run -d -p 5000:5000 server
docker run -d -p 3000:3000 client
```
## Minikube
Make sure to use the Minikube Docker daemon by running the following command
```
eval $(minikube docker-env)
```
Note: Later, when you no longer wish to use the Minikube host, you can undo this change by running:
```
eval $(minikube docker-env -u).
```
Build server docker image and start server:
```
docker build -t server .

kubectl run server --image=server --port=5000 --image-pull-policy=Never --expose=True

minikube service server
```
According to minikube server port number, modify host variable in ```public/utils/APIRoutes.js```, then build client docker image and start client
```
docker build -t client .

kubectl run server --image=client --port=5000 --image-pull-policy=Never --expose=True

minikube service client
```

## Requirements Pointer
### Overview
1. Frontend: react
2. Backend: Node.js
3. Protocal: RESTful, Websockets
4. Database: MongoDB
5. Infrastructure: Docker + Minikube

### Frontend
1. Video 00:00
2. Video 00:35
3. Video 01:10
4. Video 01:15
5. Video 01:30
6. Video 

## Backend
1. ```server/controllers/userController.js register```
2. ```server/controllers/userController.js login```
3. ```server/controllers/userController.js login```
4. ```server/controllers/messageController.js addMessage```
5. In currect application, upvote and downvote are handled as automatic messages. In other scenarios, Mongodb also uses locking and concurrency control to prevent clients modifying the same data simultaneously.
6. ```server/controllers/userController.js login```