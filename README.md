# 🚀 Projet Cloud-Native App Delivery

## 📦 TechLogix Inventory Application

Ce projet démontre une chaîne de livraison complète pour une application cloud-native :
- **Conteneurisation** avec Docker
- **CI/CD** avec GitHub Actions
- **Orchestration** avec Kubernetes (Minikube)




Construire l'image Docker

commande: docker build -t techlogix-inventory:local .

![Build image docker](https://imgur.com/jaPxkYU)



Lancer le conteneur

commande: "docker run -d -p 3000:3000 --name inventory-test techlogix-inventory:local"

![run docker](https://imgur.com/nO7DgfD)


Tester l'application

URL: http://localhost:3000

![Test image en local](https://imgur.com/fV2cKpY)



Pipeline automatisé avec Github Action
À chaque git push sur la branche main :

.Build de l'image Docker

.Connexion à Docker Hub
![workflow avec GitHub Action](https://imgur.com/i6LgEiE)

.Push de l'image avec les tags latest et v1.0
![Push de l'image sur DockerHub](https://imgur.com/DOpvxtw)


Déploiement Kubernetes

1. Démarrer Minikube

commande: minikube start --driver=docker --memory=2560 --cpus=2

![Demarrage Minikube](https://imgur.com/ltiJCG9)



2. Déployer l'application

# Appliquer les manifests

kubectl apply -f k8s/deployment.yml"

kubectl apply -f k8s/service.yml"

![Application de deployment et service](https://imgur.com/6gIQKO4)


# Vérifier le déploiement
kubectl get 

kubectl get deployments

kubectl get services

![verification du deploiement](https://imgur.com/6pyB33n)



3. Accéder à l'application

minikube service techlogix-inventory-service --url

URL: http://127.0.0.1:61345

![Acceder a l'applicaion via l'IP du cluster](https://imgur.com/ic12mHh)




Quelques commandes utiles:
docker images,

docker ps -a,

docker stop <nom conteneur>,

docker rm <nom conteneur>,

kubectl delete -f <nom fichier>,

minikube stop,

minikube delete,

minikube dashboard


