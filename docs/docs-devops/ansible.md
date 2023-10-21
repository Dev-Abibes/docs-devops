---
sidebar_position: 4
---

# Guide d'utilisation Ansible

:::tip Ansible

Apprendre Ansible

:::

## Installation d'Ansible

Pour commencer, installez Ansible sur la machine à partir de laquelle vous souhaitez gérer vos serveurs.

### Sur Linux

```js
    sudo apt update
    sudo apt install ansible
// mac os
    brew install ansible
```
#### fichier inventory.ini 
```js
    # inventory.ini
    [serveurs]
    serveur1 ansible_host=adresse_ip_ou_nom_de_domaine
    serveur2 ansible_host=adresse_ip_ou_nom_de_domaine
```
### Configuration SSH :
Assurez-vous que vous avez des clés SSH configurées pour vous connecter aux serveurs sans mot de passe.

```js
// deployment_wordpress.yml

- hosts: kubernetes_master
  become: true
  tasks:
    - name: Déploiement de WordPress
      k8s:
        state: present
        definition:
          apiVersion: apps/v1
          kind: Deployment
          metadata:
            name: wordpress-deployment
          spec:
            replicas: 3
            selector:
              matchLabels:
                app: wordpress
            template:
              metadata:
                labels:
                  app: wordpress
              spec:
                containers:
                - name: wordpress-container
                  image: wordpress:latest
                  ports:
                  - containerPort: 80
                  env:
                  - name: WORDPRESS_DB_HOST
                    value: "mysql-service"
                  - name: WORDPRESS_DB_USER
                    value: "root"
                  - name: WORDPRESS_DB_PASSWORD
                    value: "password"
                  - name: WORDPRESS_DB_NAME
                    value: "wordpress"

    - name: Service MySQL
      k8s:
        state: present
        definition:
          apiVersion: v1
          kind: Service
          metadata:
            name: mysql-service
          spec:
            selector:
              app: wordpress
            ports:
            - protocol: TCP
              port: 3306
              targetPort: 3306

    - name: Service WordPress
      k8s:
        state: present
        definition:
          apiVersion: v1
          kind: Service
          metadata:
            name: wordpress-service
          spec:
            selector:
              app: wordpress
            ports:
            - protocol: TCP
              port: 80
              targetPort: 80
            type: LoadBalancer
```

### La Commande
```js
ansible-playbook -i inventory.ini deployment_wordpress.yml
```







