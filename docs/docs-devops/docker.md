---
sidebar_position: 4
---


# Guide d'Utilisation Docker pour Débutants



## Qu'est-ce que Docker ?

[Docker](https://www.docker.com/) est une plateforme open-source qui permet d'automatiser le déploiement, la gestion et le dimensionnement d'applications dans des conteneurs. Les conteneurs Docker encapsulent une application et ses dépendances, garantissant une exécution cohérente indépendamment de l'environnement.

## Installation de Docker

### Linux

### 1. Sur Ubuntu, exécutez les commandes suivantes :
 ```js
   sudo apt update
   sudo apt install docker.io
```
### Démarrez le service Docker :
```js
sudo systemctl start docker
```
### 1. Vérifier l'installation

```js
docker --version
docker info
```
### 2. Télécharger une image Docker

```js
docker pull nom_image
```
### 3. Exécuter un conteneur
```js
docker run nom_image
```
### 4. Liste des conteneurs en cours d'exécution

```js
docker ps
```
### 5. Liste de toutes les images téléchargées
```js
docker images
```
### 6. Arrêter un conteneur
```js
docker stop id_conteneur
```
### 7. Supprimer un conteneur
```js
docker rm id_conteneur
```
### 8. Exécuter une commande dans un conteneur en cours d'exécution
```js
docker exec -it id_conteneur commande /bin/bash
```

### dockerfile

```js
# Utiliser une image de base
FROM ubuntu:latest

# Copier des fichiers dans l'image
COPY . /app

# Spécifier le répertoire de travail
WORKDIR /app

# Exécuter une commande lors de la création de l'image
RUN apt-get update && apt-get install -y python3

# Exposer un port
EXPOSE 80

# Commande par défaut lors du lancement du conteneur
CMD ["python3", "app.py"]

```
### Docker compose
Exemple de docker compose avec l'image Nginx

```js

version: '3.8'

services:
  nginx:
    image: nginx:latest
    container_name: mon_nginx
    ports:
      - "8080:80"
    volumes:
      - ./site:/usr/share/nginx/html
      - ./nginx/conf.d:/etc/nginx/conf.d
      - ./nginx/nginx.conf:/etc/nginx/nginx.conf
    restart: always
    environment:
      - NGINX_HOST=mon_domaine.com
      - NGINX_PORT=80
    networks:
      - mon_reseau

networks:
  mon_reseau:
    driver: bridge
```

```sh
//execution de docker compose
docker-compose up -d

// voir si l'image est crée et le container aussi
docker images
docker ps // les containers en running
docker ps -a // Tous les containers 
```