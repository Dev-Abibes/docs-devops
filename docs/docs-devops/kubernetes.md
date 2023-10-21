---
sidebar_position: 4
---

Installation de Kubernetes sur Linux
Sur Linux, un moyen courant d'installer Kubernetes est d'utiliser kubeadm, kubectl, et kubelet. Voici les étapes générales :

## Installer kubeadm, kubectl et kubelet :
```js
    sudo apt-get update && sudo apt-get install -y apt-transport-https curl
    curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
    echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
    sudo apt-get update
    sudo apt-get install -y kubeadm kubectl kubelet

//Initialiser le cluster (sur le nœud maître) :

sudo kubeadm init
//Configurer kubectl (sur le nœud maître) :
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

//Installer un réseau de pod (par exemple, Calico) :
kubectl apply -f https://docs.projectcalico.org/v3.20/manifests/calico.yaml

```
### Installation de Kubernetes sur macOS
Sur macOS, un moyen courant d'installer Kubernetes est d'utiliser Minikube, qui crée un cluster Kubernetes unique en machine virtuelle. Voici les étapes :

#### Installer Minikube (et kubectl, si ce n'est pas déjà fait) :
```js
brew install minikube kubectl
minikube start
minikube status
minikube stop
minikube delete
minikube dashboard
minikube ssh

```

### Commandes kubectl

```js
// Afficher les déploiements :
kubectl get deployments

// Afficher les détails d'un déploiement :
kubectl describe deployment [nom_du_deploiement]

//Exposer un déploiement en tant que service :
kubectl expose deployment [nom_du_deploiement] --type=NodePort --port=[port]

// Afficher les services :
kubectl get services

```

## Gestion des ConfigMaps et Secrets

```js
// Créer une ConfigMap à partir d'un fichier :
kubectl create configmap [nom_de_la_configmap] --from-file=fichier.txt

// Créer un Secret à partir d'un fichier :
kubectl create secret generic [nom_du_secret] --from-file=fichier.txt

// Afficher les namespaces :
kubectl get namespaces

// Changer le namespace par défaut :
kubectl config set-context --current --namespace=[nom_du_namespace]

```
#### fichier: mon_app_deployment.yaml
```js
// fichier: wordpress_deployment.yaml

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

---

// fichier: mysql_service.yaml

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

---

// fichier: wordpress_service.yaml

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
### Les Commandes d'exécution
```js
kubectl apply -f mon_app_deployment.yaml
kubectl apply -f mon_app_service.yaml
```




