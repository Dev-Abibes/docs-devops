---
sidebar_position: 4
---

# Guide d'Utilisation de Git

### Configuration du compte :
```js
git config --global user.name "Votre Nom" : Configure le nom d'utilisateur.
git config --global user.email "votre@email.com" : Configure l'adresse e-mail.
```
### Gestion des Dépôts :
```js
git init : //Initialise un nouveau dépôt.
git clone <URL> : //Clone un dépôt distant.
```
### Gestion des Fichiers :
```js
git add <fichier> : Ajoute un fichier à l'index.
//ou
git add . : // tous les fichies modifiés
git commit -m "Message:  le premier commit" : //Valide les changements avec un message de commit.
```
### Branches :
```js
git branch : Liste toutes les branches.
git branch <stagging> : //Crée une nouvelle branche.
git checkout <stagging> : //Bascule vers une branche spécifique.
git merge <main> : //Fusionne une branche dans la branche active.
```
### Récupération et Envoi :
```js
git pull origin <main> : //Récupère les modifications depuis le dépôt distant.
git push origin <main> : //Envoie les modifications vers le dépôt distant.
```
### Historique et Annulations :
```js
git log : //Affiche l'historique des validations.
git revert <commit> : //Annule les modifications d'un commit.
git reset --hard <commit> : //Revertit le dépôt à un commit spécifique.
```
### Modification des Commits :
```js
git commit --amend : //Modifie le dernier commit.
git rebase -i <commit> : //Réorganise et modifie les commits.
```
### Gestion des Remotes :
```js
git remote -v : //Affiche les URLs des remotes
git remote add <nom> <URL> : //Ajoute un remote
git remote remove <nom> : //Supprime un remote
```
### Gestion des Tags :
```js
git tag : Liste les tags existants.
git tag -a <nom_tag> -m "Message" : //Ajoute un tag annoté.
```
### Autres Commandes Utiles :
```js
git status : // Affiche l'état des fichiers.
git diff : // Montre les différences entre les commits, les fichiers, etc.
git stash : // Enregistre temporairement les modifications non validées.
git fetch : // Récupère les modifications depuis le remote, sans fusionner.
```