# Improper Input Validation - 3 - Upload Type

## Outil utilisé

* **Burp Suite Community** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

J’ai préparé un fichier avec une extension autorisée `.pdf`, puis je l’ai uploadé. Ensuite, j’ai intercepté la requête d’upload avec Burp et modifié l’extension et il a été accepté malgré les restrictions.

## Vulnérabilité

* La vérification de l'extension se fait uniquement côté client et peut être contournée.

## Risques

* Upload de fichiers malveillants


## Action

* Vérifier le type de fichier côté serveur

## Étapes

### 1. Aller sur la partie Complaint et accéder au formulaire afin de pouvoir envoyer un avis avec un fichier joint.

![img](../img-au-cas-ou/Upload%20Type.png)

<br>

### 2. Uploader un fichier avec une extension autorisée (`.pdf`) et écrire un avis de test, le contenu n’a pas d’importance.

![img](../img-au-cas-ou/Upload%20Type2.png)

<br>

### 3. Intercepter la requête d’upload avec Burp Suite et repérer la ligne où l’extension ou le format du fichier est défini.

![img](../img-au-cas-ou/Upload%20Type3.png)

<br>

### 4. Modifier l’extension du fichier dans la requête (ex : passer de `.pdf` à `.txt`), puis envoyer la requête modifiée.

![img](../img-au-cas-ou/Upload%20Type4.png)

<br>

### 5. Retourner sur le site pour constater que vous avez reussi la tache.

![img](../img-au-cas-ou/Upload%20Type5.png)

