# 🚀 Projet Cloud-Native App Delivery

## 📦 TechLogix Inventory Application

Ce projet démontre une chaîne de livraison complète pour une application cloud-native :
- **Conteneurisation** avec Docker
- **CI/CD** avec GitHub Actions
- **Orchestration** avec Kubernetes (Minikube)




# I. Construire l'image Docker

commande: docker build -t techlogix-inventory:local .

 Cette image l'illustre  
 
 ![Build image docker](https://i.imgur.com/jaPxkYU.png)



# II. Lancer le conteneur

commande:  docker run -d -p 3000:3000 --name inventory-test techlogix-inventory:local

![run docker](https://i.imgur.com/nO7DgfD.png)


# III. Tester l'application
On a ensuite verifier si l'image s'affiche avec l'URL ci-dessous

URL: http://localhost:3000

Cette image nous le montre 

![Test image en local](https://i.imgur.com/X29ONsp.jpeg)



# IV. Pipeline automatisé avec Github Action
À chaque git push sur la branche main :

.Build de l'image Docker

.Connexion à Docker 

![workflow avec GitHub Action](https://i.imgur.com/i6LgEiE.jpeg)

.Push de l'image avec les tags latest et v1.0

On a ensuite pousser l'image dans DockerHub

Cette image nous montre l'image avec ses differentes version  

![Push de l'image sur DockerHub](https://i.imgur.com/DOpvxtw.jpeg)


# V. Déploiement Kubernetes
Pour la partie Kubernetes on a utilise Minikube (k8s)

1. Démarrer Minikube

commande: minikube start --driver=docker --memory=2560 --cpus=2

![Demarrage Minikube](https://i.imgur.com/ltiJCG9.png)



2. Déployer l'application

## Appliquer les manifests

Commande 1:  kubectl apply -f k8s/deployment.yml"

Commande 2:  kubectl apply -f k8s/service.yml"

![Application de deployment et service](https://i.imgur.com/6gIQKO4.png)

p
## Vérifier le déploiement

Commande 1:  kubectl get all

Commande 2:  kubectl get deployments

Commande 3:  kubectl get services


![verification du deploiement](https://i.imgur.com/6pyB33n.png)


3. Accéder à l'application

On a reussi a deploiyer l'application avec Kubernetes grace a l'IP du cluster

Commande:  minikube service techlogix-inventory-service --url

URL: http://127.0.0.1:61345

![Acceder a l'applicaion via l'IP du cluster](https://i.imgur.com/fV2cKpY.jpeg)




# Quelques commandes utiles:

docker images,

docker ps -a,

docker stop <nom conteneur>,

docker rm <nom conteneur>,

kubectl delete -f <nom fichier>,

minikube stop,

minikube delete,

minikube dashboard


