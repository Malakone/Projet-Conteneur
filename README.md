# 🚀 Projet Cloud-Native App Delivery

## 📦 TechLogix Inventory Application

Ce projet démontre une chaîne de livraison complète pour une application cloud-native :
- **Conteneurisation** avec Docker
- **CI/CD** avec GitHub Actions
- **Orchestration** avec Kubernetes (Minikube)




# I. Construire l'image Docker

commande: docker build -t techlogix-inventory:local .

 Cette image l'illustre  ![Build image docker](https://imgur.com/jaPxkYU)



# II. Lancer le conteneur

commande:  docker run -d -p 3000:3000 --name inventory-test techlogix-inventory:local

![run docker](https://imgur.com/nO7DgfD)


# III. Tester l'application
On a ensuite verifier si l'image s'affiche avec l'URL ci-dessous

URL: http://localhost:3000

Cette image nous le montre ![Test image en local](https://imgur.com/fV2cKpY)



# IV. Pipeline automatisé avec Github Action
À chaque git push sur la branche main :

.Build de l'image Docker

.Connexion à Docker Hub
![workflow avec GitHub Action](https://imgur.com/i6LgEiE)

.Push de l'image avec les tags latest et v1.0

On a ensuite pousser l'image dans DockerHub

![Push de l'image sur DockerHub](https://imgur.com/DOpvxtw)


# V. Déploiement Kubernetes

1. Démarrer Minikube

commande: minikube start --driver=docker --memory=2560 --cpus=2

![Demarrage Minikube](https://imgur.com/ltiJCG9)



2. Déployer l'application

## Appliquer les manifests

Commande 1:  kubectl apply -f k8s/deployment.yml"

Commande 2:  kubectl apply -f k8s/service.yml"

![Application de deployment et service](https://imgur.com/6gIQKO4)


## Vérifier le déploiement

Commande 1:  kubectl get 

Commande 2:  kubectl get deployments

Commande 3:  kubectl get services

![verification du deploiement](https://imgur.com/6pyB33n)



3. Accéder à l'application

On a reussi a deploiyer l'application avec Kubernetes grace a l'IP du cluster

Commande:  minikube service techlogix-inventory-service --url

URL: http://127.0.0.1:61345

![Acceder a l'applicaion via l'IP du cluster](https://imgur.com/ic12mHh)




# Quelques commandes utiles:
docker images,

docker ps -a,

docker stop <nom conteneur>,

docker rm <nom conteneur>,

kubectl delete -f <nom fichier>,

minikube stop,

minikube delete,

minikube dashboard


