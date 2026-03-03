## Languages

- js
- php
- scss/css
- html (twig)
- sql MySQL

## Frameworks

- Slim
- Twig

## Principe de l'appli

C'est une sorte de leboncoin. Une appli où on peut consulter/publier des annonces.

## Première Etape

Il n'y pas de BDD en local, il faut l'ajouter dans le docker.
Il faut un fichier config.ini dans le dossier config sinon l'application marche pas.
-> Le problème c'est qu'on ne sait pas quoi mettre dedans car il n'y a pas de fichier example.

## Problèmes identifiés

css qui ne devrait pas être là puisqu'il y a du scss qui le génère
README vide

Route pas sécurisée /config/config.ini

## Faire marcher l'application

Installer/Mettre à jour les dépendances -> ```composer install```

Créer le fichier config.ini dans le dossier config :

```
driver=mysql
host=db
database=racoin
username=
password=
port=3306
charset=utf8
```

Lancer l'application : ```docker compose up -d --build```

## TODO Améliorations

- Sécuriser les routes, actuellement chaque fichier du projet est en fait accessible via une requête. Le fichier index.php est à la racine du projet, il faudrait le mettre dans un dossier public avec les autres fichiers censés être accessibles (comme les fichiers js). **Temps 2/10 Impact 10/10**
- Version de twig 1.0 à changer, passer directement à la version 3.x ou la plus récente. C'est un gros gap de version qui peut entrainer des problèmes. Le projet n'est qu'en twig 1.0, changer de version itérativement est trop fastidieux à ce stade. La version du projet actuel contient de failles importantes. **Temps 3/10 Impact 6/10**
- Version de symfony 4.0 à changer, passer directement à la version la plus récente. La version du projet actuel contient des failles critiques. Hormis les versions les plus récentes, symfony n'a pas d'autre version maintenue **+** Version de slim toujours ok, mais il serait quand même bon de passer aux versions récentes. **Temps 5/10 Impact 5/10**
- Fichiers CSS à mettre dans le gitignore, les fichiers SCSS sont censés les générer donc pas besoin de les garder. **Temps 1/10 Impact 2/10**
- Pas mal de code en notation, rien de dramatique mais il faudrait quand même nettoyer. **Temps 1/10 Impact 1/10**
