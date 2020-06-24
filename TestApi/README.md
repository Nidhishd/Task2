Installation and setup of minikube
================

Follow the guide https://kubernetes.io/docs/tasks/tools/install-minikube/ for the minikube binary setup

>> sudo minikube start --vm-driver=none

I started minikube without any vm option for easy and fast setup

>> sudo minikube status

To check status of minikube

Deploy API application and nginx
================================

Create a namespace "dev" , I used "dev" namespace to deploy this application

>> kubectl create ns dev

>>
kubectl create -f k8s/k8s.yaml

This will deploy application in dev namespace

>> kubectl create -f nginx/nginx.yaml

This will deploy nginx in dev namespace

Accessing the api
=================

We need to portforward the API application

1. Find the pods for the application

kubectl get pods -n dev

kubectl -n dev port-forward POD_NAME 5001:5001

2. open broswer and call https://127.0.0.1:5001/weatherforecast/fetch,  https://127.0.0.1:5001/weatherforecast