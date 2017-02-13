# Configuration du serveur
## Gestions des droits
Passez en root avec la commande `su` puis tapez votre mot de passe root.
ensuite mettez les dépendances à jour :
 `apt-get update && apt-get upgrade`
 
ajoutez la dépendance `sudo`
```bash
apt-get install sudo
```
puis tapez la commande suivante pour ajouter l’utilisateur au groupe sudo
```bash
adduser user sudo
```
ensuite tapez la commande `visudo` et ajoutez cette ligne en dessous de la ligne root
```
user ALL=(ALL:ALL) ALL
```
enregistrez le fichier puis tapez `exit` pour sortir du mode root

## Vim
Création d'un fichier `.vimrc` :
```bash
syntax on
set number
set tabstop=4 shiftwidth=4 expandtab
```
À mettre dans chaque répertoire personel ou l'on utilise vim (root compris)

## SSH
### Changer le port ssh
Éditez le fichier suivant : `/etc/ssh/sshd_config`
Puis changer la ligne 5 **Port 22** avec le port souhaité.
Enregistrez le fichier et tapez la commande suivante
```bash
sudo service ssh restart
```

### Utiliser une clé ssh





