# Git et Github

## A. Intro

**Git** est un logiciel de versioning créé en 2005 par _Linus Torvalds, le_ créateur de Linux.

Git est un **système de gestion de versions**, qui permet de stocker de manière optimisée et sécurisée des fichiers et toutes leurs modifications dans le temps. Il permet donc de conserver un historique des modifications effectuées sur un projet afin de pouvoir rapidement identifier les changements effectués et de revenir à une ancienne version en cas de problème.

**GitHub** est une plateforme permettant d'héberger et gérer ces différents projets web (il en existe d'autres comme GitLab...)

En plus de **mémoriser un historiques** des différentes versions de votre code, GitHub permettent un **travail collaboratif**. Ainsi plusieurs personnes peuvent travailler ensemble sur le même projet et intégrer harmonieusement leurs travaux respectifs.

### \_Les Mots de Git

**Ligne de Commande** : Le programme de l’ordinateur que nous utilisons pour entrer des commandes Git. Sur un Mac, ça s’appelle Terminal. Sur un PC, c’est un programme non-natif que vous téléchargez lorsque vous téléchargez Git pour la première fois. Dans les deux cas, vous tapez à l’écran des commandes à base de texte, appelées invites de commande, au lieu d’utiliser une souris.

**Dépôt / repository** : Un répertoire ou un espace de stockage où vos projets peuvent vivre. Il peut être local sur un répertoire de votre ordinateur, ou ce peut être un espace de stockage sur GitHub ou un autre hébergeur en ligne. À l’intérieur d’un dépôt, vous pouvez conserver des fichiers de code, des fichiers texte, des images.

**Contrôle de Version** : Fondamentalement, l’objectif pour lequel Git a été conçu. Quand vous avez un fichier quelconque, vous l’écrasez à chaque fois que vous faites une nouvelle sauvegarde, ou vous sauvegardez plusieurs versions. Avec Git, vous n’êtes plus obligé de faire ça. Git conserve des « instantanés » de chaque point dans l’historique d’un projet, de sorte que vous ne pouvez jamais le perdre ou l’écraser.

**Commit** : C’est la commande qui donne à Git toute sa puissance. Quand vous « committez », vous prenez un « instantané », une « photo » de votre dépôt à ce stade, vous donnant un point de contrôle que vous pouvez ensuite réévaluer ou restaurer votre projet à un état précédent.

**Branche** : Comment faire travailler plusieurs personnes sur un projet en même temps sans que Git ne s’embrouille ? Habituellement, elles se « débranchent » du projet principal avec leurs propres versions complètes des modifications qu’elles ont chacune produites de leur côté. Après avoir terminé, il est temps de « fusionner » cette branche pour la ramener vers la branche « master », le répertoire principal du projet.

## B. Mise en place

### 1. Création d'un compte GitHub

Pour commencer, vous devez créer un compte sur GitHub, avec lequel vous pourrez héberger vos projets et collaborer avec d'autres personnes.

Créer un compte avec votre `adresse mail universitaire` et un identifiant sous le forme `prenom-nom`.

### 2. Installation de GIT sur votre ordinateur

#### \_Ordinateur de l'IUT

> Sur les ordinateurs de l'IUT **auncune installation n'est nécessaire**, Git est déjà installé.

#### \_Ordinateur personnel

Pour vérifier si Git est installé sur votre ordinateur, ouvrez VSCode, puis le terminal et tapez la commande suivante :

```bash
    git --version
```

Si Git est installé, vous devriez voir s'afficher la version de Git installée sur votre ordinateur.

##### Installation de Git sur Windows

Visitez le site: https://git-scm.com/downloads, téléchargez l'installateur GIT pour Windows et double-cliquez l'exécutable pour lancer l'assistant d'installation. Dans la fenêtre Sélectionner les composants, laissez toutes les options par défaut cochées

##### Installation de Git sur Mac

Visitez le site: https://git-scm.com/downloads/mac
Le plus simple, mais le plus long est d'installer Xcode.

### 3. Paramétrage de Git

Git est un logiciel en ligne de commande, ce qui signifie que vous allez devoir taper des commandes pour l’utiliser. Les commandes Git suivent un modèle simple :

```bash
    git commande paramètre1 paramètre2  --option
```

Ici `commande` représente la fonction spécifique à exécuter par Git.
Si certaines fonctions de Git se suffisent d’un nom de commande (comme git status), la plupart nécessitent des paramètres et/ou des options.

#### \_Configuration de Git

Une fois Git installé, nous allons paramétrer le logiciel afin d’enregistrer certaines données.

Dans le terminal exécutez la commande suivante pour définir votre nom et email

```bash
    git config --global user.name "Votre nom"
    git config --global user.email "votreEmail@unilim.fr"
```

Ici, l’option `--global` va nous permettre d’indiquer à Git que le nom d’utilisateur et l’adresse mail renseignés doivent être utilisés globalement (c’est-à-dire pour tout projet Git).

Vérifiez vos paramètres :

Pour vous assurer que vos informations ont bien été enregistrées, vous pouvez taper `git config user.name` et `git config user.email`.

Si vous souhaitez vérifier vos réglages, vous pouvez utiliser la commande `git config --list` pour lister tous les réglages que Git a pu trouver jusqu’ici

### 4. Démarrer

#### 4.1 À partir d'un répertoire existant

[x] Créez sur Github un nouveau dépôt nommé `R212`
[x] Créez un dossier sur votre ordinateur, nommé `R212`
[x] Créer un fichier `README.md` dans ce dossier, et ajoutez-y un titre et une description de votre projet.
[x] Ouvrir ce dossier dans VSCode, ouvrir le terminal et tapez les commandes suivantes :

```bash
    git init
    git remote add origin https://github.com/[nom utilisateur]/R212.git
```

#### 4.2 En clonant un dépôt existant

[x] Cloner le dépôt sur votre ordinateur.

### 5. Modifier et envoyer des fichiers

[x] Modifier votre fichier README.md.
[x] Dans la barre d'outils de VSCode, cliquer sur l'icône `Source Control` (Ctrl+Shift+G) - celui-ci doit afficher un `1` pour indiquer qu'il y a un fichier modifié en attente.
[x] Cliquer sur `+` pour ajouter le fichier modifié à la liste des fichiers à commiter.
[x] Saisir un message de commit dans la zone de texte `Message` en haut de l'écran.
[x] Cliquer sur la coche pour valider le commit.
[x] Cliquer sur les `...` à droite de la barre d'outils et sélectionner `Push` pour envoyer vos modifications sur Github.

**Vous venez de réaliser votre premier commit et push sur Github.**

![GitHub](./assets/Git.png)
