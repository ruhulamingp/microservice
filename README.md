[![Build Status](https://travis-ci.com/ruhulamingp/microservice.svg?branch=master)](https://travis-ci.com/ruhulamingp/microservice)

### Udagram-microservices

#### Github link:
https://github.com/ruhulamingp/microservice

### Dockerhub Link:
https://hub.docker.com/repository/docker/ruhulamingp/udacity-frontend
https://hub.docker.com/repository/docker/ruhulamingp/udacity-restapi-feed
https://hub.docker.com/repository/docker/ruhulamingp/udacity-restapi-user
https://hub.docker.com/repository/docker/ruhulamingp/reverseproxy

### Kubernetes Deployment
Created Kubernetes cluster using minikube

minikube start --vm-driver=none

### Create Own secret and config file

mv udacity-c3-deployment/k8s/samples/aws-secret-sample.yaml udacity-c3-deployment/k8s/aws-secret.yaml
mv udacity-c3-deployment/k8s/samples/env-secret-sample.yaml udacity-c3-deployment/k8s/env-secret.yaml
mv udacity-c3-deployment/k8s/samples/env-configmap-sample.yaml udacity-c3-deployment/k8s/env-configmap.yaml

### Deploy application using services and deployment

kubectl convert  -f . | kubectl apply -f -

### Check Cluster status

kubectl get all

### Expose frontend and reverse proxy through port forward

    kubectl port-forward service/reverseproxy 8080:31005
    kubectl port-forward service/frontend 8100:31000
