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

## Curl et Git

Installez les packages suivants :
```bash
sudo apt-get install curl git
```

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

## ZSH

Installation du package :
```bash
sudo apt-get install zsh
```

Une fois l'installation terminé taper la commande `zsh`
Appuyer sur `2` pour créer le fichier de configuration par défaut

### installation de oh-my-zsh
[Github de oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)

Entrez la commande suivante :
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
Entrez votre mot de passe utilisateur quand on vous le demandera

### Thème pure
[Github du thème pure](https://github.com/sindresorhus/pure)
*ATTENTION: Ce thème à besoin d'une font particulière de base*

Clonez le dépot du thème pure et copiez-y les fichiers :
```bash
git clone https://github.com/sindresorhus/pure.git

cp pure/pure.plugin.zsh .oh-my-zsh/themes/pure.zsh-theme
cp pure/async.zsh .oh-my-zsh/custom/async.zsh
```
Modifier votre fichier `.zshrc` en remplaçant le **ZSH_THEME=** :
```bash
ZSH_THEME="pure"
```
Une fois finis faite ceci pour reload la configuration :
```bash
source .zshrc
```

### Plugin zsh-syntax-highlighting
[Github du plugin](https://github.com/zsh-users/zsh-syntax-highlighting)

Installer le plugin dans oh-my-zsh comme ceci :
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
Modifier votre fichier `.zshrc` et ajouter le plugin:
```bash
plugin=([plugins...] zsh-syntax-highlighting)
```
Une fois finis faite ceci pour reload la configuration :
```bash
source .zshrc
```
