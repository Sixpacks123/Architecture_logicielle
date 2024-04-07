# Microservices avec Nest.js, NATS, MySQL et Docker

Ce dépôt contient trois projets Nest.js :

- **http-api-gateway** : Passerelle API HTTP
- **payments-microservice** : Microservice de paiements
- **users-microservice** : Microservice d'utilisateurs

## Prérequis

- Docker
- Node.js
- npm


### Lancement du projet


```bash
docker-compose up --build
```

## Structure de l'application

### http-api-gateway

C'est une application hybride utilisant HTTP et NATS comme sources pour écouter les requêtes. Elle sert de point d'entrée à la plateforme, redirigeant les requêtes en publiant un message au serveur NATS, qui les distribue ensuite à ses abonnés.

### payments-microservice

Ce microservice réagit à l'événement `createPayment` envoyé par le serveur NATS. Il crée un enregistrement de paiement et le sauvegarde dans la base de données.

### users-microservice

Ce microservice réagit à l'événement `createUser` envoyé par le serveur NATS. Il crée un enregistrement utilisateur et le sauvegarde dans la base de données.


## TODO:
- Add SonarQube
- Add Grafana
- Change Docker compose for Docker swarn for add loadbalancind app
- Add ngnix
