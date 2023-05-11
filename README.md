# Test project to create docker image and run that image on minikube

## A fully functional Example to create a Node js image in docker and load that image in minikube without using container regestry like Docker hub or gcr.io this projects uses local minikube docker to generate and use image created locally

this is project is to demonstrate how you can use GitHub codespace to learn basics of Docker and Minikube to get clear understanding of containers and kubernetes.

* Create a blank codespace 
* Verify Docker installation
* Create a basic Docker Image
* Run Docker image 
* Verify Minikube installation
* Create image that minikube can
* Create a deployment file for app 
* Deploy the app 
* Create Service to Expose port 
* Verify the app using services running in minikube 


### Design Doc
-- Work in progress please review attached word doc 
https://github.com/jigar3730/DockerMinikube/blob/main/Docker_minikube%20in%20codespaces.docx

### Commands used 
```sh
minikube status
minikube start
eval $(minikube docker-env)
cd project1/
docker build -t project1:01 .
docker images
source <(kubectl completion bash)
minikube dashboard --url
kubectl create deploy app1 --image=node-app:0.2 --replicas=3 -dry-run=client -o yaml >myapp.yaml
docker images
kubectl create deploy app1 --image=project1:01 --replicas=3 --dry-run=client -o yaml >myapp.yaml
cat myapp.yaml 
kubectl create deploy -h
kubectl create deploy app1 --image=node-app:0.2 --replicas=3 --port=80 --dry-run=client -o yaml >myapp.yaml
kubectl apply -f myapp.yaml 
kubectl get all
minikube dashboard --url
kubectl delete deployment app1 
rm myapp.yaml 
docker build -t project1:01 .
kubectl get deployment myfirstapp 
kubectl describe  deployment myfirstapp 
minikube ip
kubectl delete deployment myfirstapp 
kubectl create deploy myfirstapp --image=project1:01 --replicas=5
kubectl expose deployment myfirstapp --type=LoadBalancer --port=80
kubectl get services
minikube service project1 --url
minikube service myfirstapp --url
kubectl delete deployment myfirstapp
kubectl delete service myfirstapp 
kubectl create deploy firstapp --image=project1:01 --replicas=3 --http-port=80 --dry-run=client -o yaml >firstapp.yaml
kubectl create deploy firstapp --image=project1:01 --replicas=3 --port=80 --dry-run=client -o yaml >firstapp.yaml
rm myapp.yaml 
cat firstapp.yaml 
kubectl  apply -f firstapp.yaml 
kubectl expose deployment -h
kubectl expose deployment firstapp --port=80 --traget-port=8000
kubectl expose deployment firstapp --port=80
kubectl get services
minikube service firstapp --url
```

### Know how could this be done better 
please provide feedback or report issus and help improve.



