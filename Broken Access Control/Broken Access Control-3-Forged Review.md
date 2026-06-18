# Broken Access Control - 3 - Forged Review

## Outil utilisé

* **Burp Suite Community** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

la méthode est la même que pour le forged feedback.  

j’ai posté une review avec un compte normal sur le site puis j’ai intercepté la requete dans burp puis j'ai changé l’id utilisateur et renvoyé la requete pour que la review apparaisse sous un autre compte.

## Vulnérabilité

Comme pour le forged feedback, l’app accepte un id utilisateur modifié, ce qui peux nuire l'experience utilisateurs falsifier des informations

## Risques

* review envoyée sous une autre identité
* usurpation simple

## Action

* Comme pour le forged feedback, il faut vérifier les informations côté serveur (ID utilisateur,  champs sensibles et contrôle d’accès).

## Étapes

> ⚠️ la méthode est identique à l’exercice précédent **Forged Feedback**.


### 1. Aller sur un article du site afin de pouvoir écrire un avis.

![img](../img-au-cas-ou/Forged%20Review.png)

<br>

### 2. Trouver la requête avec Burp Suite après l’envoi qui est `PUT /rest/products/1/reviews HTTP/2`.

![img](../img-au-cas-ou/Forged%20Review2.png)

<br>

### 3. Modifier l’email utilisateur dans le champ de l’objet JSON de la requête interceptée, puis envoyer

![img](../img-au-cas-ou/Forged%20Review3.png)

<br>

### 4. Retourner sur le site pour constater que vous avez reussi la tache.

![img](../img-au-cas-ou/Forged%20Review4.png)