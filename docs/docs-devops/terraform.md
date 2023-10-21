---
sidebar_position: 4
---

## Guide Débutant Terraform
### Installation de Terraform

Pour commencer, installez Terraform sur votre machine. Vous pouvez le télécharger depuis le site officiel de Terraform.

### Configuration de Terraform
Créez un fichier main.tf pour définir votre configuration **Terraform**. 
Ce fichier contient la description de l'infrastructure que vous souhaitez creer

```js
// main.tf
provider "provider_name" {
  # Configurations spécifiques au fournisseur
}
resource "resource_type" "resource_name" {
  # Configurations spécifiques à la ressource
}
```

- **provider_name**: Remplacez-le par le nom de votre fournisseur cloud, comme **AWS** pour Amazon Web Services.
- **resource_type**: Spécifie le type de ressource que vous souhaitez créer (par exemple, aws_instance pour une instance EC2 sur AWS).
- **resource_name**: Nom unique de votre ressource.

### Commandes Terraform de Base

```js
terraform init
terraform validate
terraform apply
terraform destroy
```

#### exemple d'utilisation ec2 aws

```js
// Supposons que vous voulez créer une instance EC2 sur AWS.
// main.tf

provider "aws" {
  region = "us-west-2"
}

// Variables
variable "aws_access_key" {}
variable "aws_secret_key" {}

// Configuration des informations d'identification AWS
provider "aws" {
  access_key = var.aws_access_key
  secret_key = var.aws_secret_key
  region     = "us-west-2"
}

// Instance EC2
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  // Configuration du pare-feu
  vpc_security_group_ids = [aws_security_group.example.id]
}

// Groupe de sécurité
resource "aws_security_group" "example" {
  name        = "example-security-group"
  description = "Allow inbound SSH and outbound traffic"

  // Règle Ingress pour SSH
  ingress {
    from_port = 22
    to_port   = 22
    protocol  = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  ingress {
  from_port = 80
  to_port   = 80
  protocol  = "tcp"
  cidr_blocks = ["0.0.0.0/0"]
}

ingress {
  from_port = 443
  to_port   = 443
  protocol  = "tcp"
  cidr_blocks = ["0.0.0.0/0"]
}

ingress {
  from_port = 25
  to_port   = 25
  protocol  = "tcp"
  cidr_blocks = ["0.0.0.0/0"]
}

ingress {
  from_port = 81
  to_port   = 81
  protocol  = "tcp"
  cidr_blocks = ["0.0.0.0/0"]
}

  // Règle Egress pour tout le trafic sortant
  egress {
    from_port = 0
    to_port   = 0
    protocol  = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```
