## Languages :

- js
- php
- scss/css
- html (twig)
- sql MySQL

## Frameworks :

- Slim
- Twig

## Principe de l'appli :

C'est une sorte de leboncoin. Une appli où on peut consulter/publier des annonces.

## Première Etape :

Il n'y pas de BDD en local, il faut l'ajouter dans le docker.
Il faut un fichier config.ini dans le dossier config sinon l'application marche pas.
-> Le problème c'est qu'on ne sait pas quoi mettre dedans car il n'y a pas de fichier example.

## Problèmes identifiés :

css qui ne devrait pas être là puisqu'il y a du scss qui le génère
README vide


## Faire marcher l'application :

Installer/Mettre à jour les dépendances -> ```composer install```

Créer le fichier config.ini dans le dossier config :

```
driver=mysql
host=db
database=racoin
username=root
password=root
port=3306
charset=utf8
```

Lancer l'application : ```docker compose up -d --build```
