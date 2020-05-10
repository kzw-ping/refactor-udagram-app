# Project 2 - Refactor Udagram App into Microservices
### Installing project dependencies

NPM Relies on the package.json file located in the root of this repository. After cloning, open your terminal and run: `npm install`

### Building the images
Create `.dockerignore` that contains `node_modules` in each root of this repository.
1. Build the images: `docker-compose -f docker-compose-build.yaml build --parallel`
2. Push the images: `docker-compose -f docker-compose-build.yaml push`

### Microservice Deployment
Create resources
1. `kubectl apply -f backend-feed-deployment.yaml` 
2. `kubectl apply -f backend-feed-service.yaml` 
3. `kubectl apply -f backend-user-deployment.yaml` 
4. `kubectl apply -f backend-user-service.yaml` 
5. `kubectl apply -f frontend-deployment.yaml`
6. `kubectl apply -f frontend-service.yaml` 
7. `kubectl apply -f reverseproxy-deployment.yaml`
8. `kubectl apply -f reverseproxy-service.yaml`
9. `kubectl apply -f pod-example/pod.yaml`
10. `kubectl apply -f aws-secret.yaml`
11. `kubectl apply -f env-configmap.yaml`
12. `kubectl apply -f env-secret.yaml`
Remark: Due to insufficient CPU, the deployment is being scaled with command `kubectl scale deployment/user --replicas=1`
***

### Running the Development Server
Open terminal and run
1. kubectl port-forward service/reverseproxy 8080:8080
2. kubectl port-forward service/frontend 8100:8100

### Github & Travis link
https://github.com/kzw-ping/refactor-udagram-app
https://travis-ci.com/github/kzw-ping/refactor-udagram-app
***