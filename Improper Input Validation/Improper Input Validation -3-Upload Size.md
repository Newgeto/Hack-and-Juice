# Improper Input Validation - 3 - Upload Size

## Outil utilisé

* **Burp Suite Community** pour intercepter et modifier les requêtes HTTP

## Méthodologie

Je suis allé sur mon compte pour modifier la photo de profil et j’ai envoyé un fichier PDF de plus de 100 KB. J’ai intercepté la requête avec Burp Suite, puis j’ai modifié l’URL de `POST /profile/image/file` vers `POST /file-upload`. Après avoir envoyé la requête et rafraîchi la page, le fichier a été accepté malgré la limite de taille.


## Vulnérabilité

* La vérification de la taille du fichier est effectuée uniquement côté client et peut être contournée.

## Risques

* Saturation de l’espace disque du serveur

## Action

* Mettre en place une vérification stricte de la taille des fichiers côté serveur


## Étapes

### 1. Aller sur le compte utilisateur et accéder à la modification de la photo de profil.

![img](../img-au-cas-ou/Upload%20Size.png)

<br>

### 2. Envoyer un fichier PDF dont la taille dépasse 100 KB via l’upload de la photo de profil.

![img](../img-au-cas-ou/Upload%20Size2.png)

<br>

### 3. Intercepter la requête `POST /profile/image/file` avec Burp Suite.

![img](../img-au-cas-ou/Upload%20Size3.png)

<br>

### 4. Modifier la requête en changeant l’URL de `POST /profile/image/file` vers `POST /file-upload`, puis envoyer la requête.

![img](../img-au-cas-ou/Upload%20Size4.png)

<br>

### 5. Retourner sur le site pour constater que la tâche a été réussie

![img](../img-au-cas-ou/Upload%20Size5.png)

