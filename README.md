## Website
This website is built using [Docusaurus 2](https://docusaurus.io/), a modern static website generator.
### Installation
```
$ yarn
```
### Local Development
```
$ yarn start
```
This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.
### Build
```
$ yarn build
```
This command generates static content into the `build` directory and can be served using any static contents hosting service.
### Deployment
Using SSH:
```
$ USE_SSH=true yarn deploy
```
Not using SSH:
```
$ GIT_USER=<Your GitHub username> yarn deploy
```
If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.
# Sommaire des Outils DevOps
:::tip Devops
learn devops
:::
#### 1. Gestion de Code Source
- **Git**: Système de contrôle de version
#### 2. Intégration Continue
- **Jenkins**: Automatisation des builds et déploiements
- **Travis CI**: Service d'intégration continue

#### 3. Automatisation de la Livraison
- **Docker**: Conteneurisation des applications [https://docs.docker.com/]
- **Kubernetes**: Orchestration de conteneurs [https://kubernetes.io/docs/home/]
- **Ansible**: Automatisation de la configuration [https://docs.ansible.com/]
- **Puppet, Chef**: Gestion de configuration [https://puppet.com/docs/]

#### 4. Surveillance et Journalisation
- **ELK Stack (Elasticsearch, Logstash, Kibana)**: Analyse de logs [https://www.elastic.co/guide/index.html]
- **Prometheus**: Surveillance et alerting [https://prometheus.io/docs/introduction/overview/]
- **Grafana**: Tableaux de bord pour la visualisation [https://grafana.com/docs/grafana-cloud/?pg=prod-cloud&plcmt=hero-btn-2]

#### 5. Gestion des Configurations
- **Terraform**: Infrastructure as Code (IaC)

#### 6. Tests Automatisés
- **Selenium**: Tests d'interface utilisateur
- **JUnit, NUnit**: Tests unitaires
- **Selenium**: Tests d'interface utilisateur
- **JUnit, NUnit**: Tests unitaires
- **PHPUnit (PHP)**: Cadre de test unitaire pour PHP
- **Jest** (JavaScript/Node.js): Cadre de test pour JavaScript
- **PyTest** (Python): Cadre de test pour Python
- **Cypress**: Tests d'interface utilisateur en JavaScript
- **Behave** (Python): Tests comportementaux en Python (BDD)
- **Mocha** (JavaScript/Node.js): Cadre de test pour JavaScript
- **Karma** (JavaScript): Cadre de test pour JavaScript
- **Robot Framework**: Automatisation de tests en Python et en Java
- **Protractor** (JavaScript/TypeScript): Cadre de test d'interface utilisateur pour les applications Angular

#### 7. Collaboration et Communication
- **Slack**: Messagerie d'équipe
- **Jira**, 
- **Trello**: Gestion de projet

#### 8. Cloud Platforms
- **AWS, Azure, Google Cloud**: Plateformes de cloud computing
- **Swisscom Cloud** (Suisse): Plateforme cloud suisse
- **OVHcloud** (Europe): Fournisseur de services cloud européen
- **Canopy Cloud** (Canada): Plateforme cloud canadienne
- **IBM Cloud** (USA, mondial): Plateforme cloud d'IBM
- **Alibaba Cloud** (Chine, mondial): Plateforme cloud d'Alibaba en Chine 
- **Tencent Cloud** (Chine, mondial): Plateforme cloud de Tencent en Chine 
- **Baidu** Cloud (Chine, mondial): Plateforme cloud de Baidu en Chine
- **Linode**

#### 9. Sécurité
- **Vault**: Gestion des secrets
- **SonarQube**: Analyse de la qualité du code
- **Vault**: Gestion des secrets
- **SonarQube**: Analyse de la qualité du code
- **OpenVAS**: Analyse de vulnérabilités
- **Snort**: Détection d'intrusion réseau
- **OSSEC**: Surveillance de la sécurité des hôtes
- **Nessus**: Scanner de vulnérabilités
- **Security Onion**: Plateforme de surveillance de la sécurité réseau
- **Wireshark**: Analyseur de protocoles réseau
- **Metasploit**: Outil de test de pénétration
- **HashiCorp Sentinel**: Validation des politiques d'infrastructure en tant que code (IaC)
- **AIDE** (Advanced Intrusion Detection Environment): Détection d'intrusions basée sur l'hôte
- **ClamAV**: Antivirus open source
- **Keycloak**: Gestion des identités et des accès
- **ModSecurity**: Pare-feu d'application web (WAF)

#### 10. Monitoring des Performances
- **New Relic, DataDog, Grafana, AppDynamics**: Surveillance des performances

#### 11. Virtualisation
- **VirtualBox, VMware**: Virtualisation
- **VirtualBox, VMware**: Virtualisation
- **KVM** (Kernel-based Virtual Machine): Infrastructure de virtualisation pour Linux
- **Hyper-V**(Microsoft): Hyperviseur de Microsoft pour Windows
- **Xen Project**: Hyperviseur open source
- **Proxmox Virtual Environment** (Proxmox VE): Plateforme de virtualisation basée sur KVM
- **Vagrant**: Gestionnaire de machines virtuelles pour le développement
- **Docker Desktop**: Virtualisation légère via des conteneurs
- **QEMU** (Quick EMUlator): Émulateur de processeur
- **Parallels Desktop** (Mac): Virtualisation sur les systèmes macOS
- **Oracle VM VirtualBox Extension Pack**: Extensions additionnelles pour VirtualBox
- **LXC** (Linux Containers): Virtualisation basée sur des conteneurs pour Linux


#### 12. Outils de Collaboration
- **GitLab, Github, Bitbucket**: Plateformes de collaboration DevOps
- **AWS CodeCommit** (Amazon EC2): Service de gestion de versions Git d'Amazon Web Services
- **Azure Repos** (Azure DevOps): Gestionnaire de dépôts Git de Microsoft Azure
- **GitBucket**: Alternative open source à GitHub, implémentable sur un serveur personnel
- **Gitea**: Service Git léger et auto-hébergé
- **GitWeb**: Interface web Git simple
- **Phabricator**: Suite d'outils de développement incluant un gestionnaire de versions
- **Apache Allura**: Plateforme open source pour le développement collaboratif de logiciels
- **RhodeCode**: Plateforme de gestion de code source avec prise en charge de Git, Mercurial et SVN
- **GitBlit**: Interface web Git simple et légère
- **SourceForge**: Plateforme de développement open source avec hébergement de code, suivi des bugs, etc.
- **GitLab CE** (Community Edition): Version open source auto-hébergée de GitLab
- **GitHub Enterprise**: Version auto-hébergée de GitHub avec des fonctionnalités avancées
- **Bitbucket Server**: Version auto-hébergée de Bitbucket
