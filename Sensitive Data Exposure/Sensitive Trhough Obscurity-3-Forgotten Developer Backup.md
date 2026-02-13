# Sensitive Trhough Obscurity - 3 - Forgotten Developer Backup

## Outil utilisé

* aucun

## Méthodologie

Je suis allé sur le FTP du site, j’ai trouvé le fichier package.json, quand j’ai cliqué dessus cela m’a renvoyé vers une page d’erreur, grâce à l’exercice sur le null byte j’ai ajouté /ftp/package.json.back%2500.md dans la barre d’adresse, ce qui m’a permis de télécharger le fichier .md du package.json.

## Vulnérabilité

* Contournable via un null byte encodé

## Risques

* Accès à des fichiers sensibles

## Étapes

### 1. Une fois sur le site, allez dans la barre de recherche, effacez `#/` et remplacez-le par `ftp` pour accéder aux fichiers du site.


![img](../img-au-cas-ou/Forgotten%20Developer%20Backup.png)

<br>

### 2. Une fois sur le FTP, cliquez sur `package.json.bak`.

![img](../img-au-cas-ou/Forgotten%20Developer%20Backup2.png)

<br>

### 3. Après avoir cliqué, vous arrivez sur cette page et dans la barre de recherche vous remplacez `package.json.bak` par `%2500.md` puis vous validez, ce qui téléchargera un fichier Markdown (texte) contenant le contenu de `package.json`. La bonne adresse `https://ctf.juice.cyber.epitest.eu/ftp/package.json.bak%2500.md`

![img](../img-au-cas-ou/Forgotten%20Developer%20Backup3.png)

<br>

### 4. Une fois terminé, retournez dans la barre de recherche, effacez tout et remettez l’adresse correcte du site (l’accueil), qui est `https://ctf.juice.cyber.epitest.eu/#/`.


![img](../img-au-cas-ou/Forgotten%20Developer%20Backup4.png)

<br>

### 5. Retourner sur le site pour constater que la tâche a été réussie

![Image 5](../img-au-cas-ou/Forgotten%20Developer%20Backup5.png)

