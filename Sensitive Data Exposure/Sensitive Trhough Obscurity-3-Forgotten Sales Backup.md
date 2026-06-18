# Sensitive Trhough Obscurity - 3 - Forgotten Sales Backup

## Outil utilisé

* aucun

## Méthodologie

Je suis allé sur le FTP du site et comme pour l’exercice Forgotten Developer Backup, j’ai appliqué la même méthode du null byte. En modifiant l’URL pour cibler le fichier coupons_2013.md.bak, j’ai pu contourner le filtrage côté serveur et récupérer le fichier du coupon.

## Vulnérabilité

* Contournable via un null byte encodé

## Risques

* Accès à des fichiers sensibles

## Étapes

> ⚠️ la méthode est identique à l’exercice précédent **Forgotten Developer Backup**.

### 1. Une fois sur le site, allez dans la barre de recherche, effacez `#/` et remplacez-le par `ftp` pour accéder aux fichiers du site.

![img](../img-au-cas-ou/Forgotten%20Developer%20Backup.png)

<br>

### 2. Une fois sur le FTP, cliquez sur `coupons_2013.md.bak`.

![img](../img-au-cas-ou/Forgotten%20Developer%20Backup2.png)

<br>

### 3. Après avoir cliqué, vous arrivez sur cette page et dans la barre de recherche vous remplacez `coupons_2013.md.bak` par `%2500.md` puis vous validez, ce qui téléchargera un fichier Markdown (texte) contenant le contenu de `coupons_2013.md`.  
La bonne adresse est `https://ctf.juice.cyber.epitest.eu/ftp/coupons_2013.md.bak%2500.md`

![img](../img-au-cas-ou/Forgotten%20Sales%20Backup.png)

<br>

### 4. Une fois terminé, retournez dans la barre de recherche, effacez tout et remettez l’adresse correcte du site (l’accueil), qui est `https://ctf.juice.cyber.epitest.eu/#/`.

![img](../img-au-cas-ou/Forgotten%20Developer%20Backup4.png)

<br>

### 5. Retourner sur le site pour constater que la tâche a été réussie

![Image 5](../img-au-cas-ou/Forgotten%20Sales%20Backup2.png)
