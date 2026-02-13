# Broken Access Control - 3 - Forged Feedback

## Outil utilisé

* **Burp Suite Community** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

J’ai envoyé un feedback sur le site avec un compte normal puis j’ai intercepté la requete dans burp, changé l’id utilisateur et renvoyé la requete pour que le feedback apparaisse sous un autre compte.

## Vulnérabilité

* l’app accepte un id utilisateur modifié, ce qui peux nuire l'experience utilisateurs falsifier des informations

## Risques

* Message envoyé sous une autre identité
* Usurpation simple

## Action

* Il faut vérifier les informations côté serveur (ID utilisateur, champs sensibles et contrôle d’accès).

## Étapes

### 1. Aller sur l’onglet Feedback du site afin de pouvoir envoyer un message.

![img](../img-au-cas-ou/Forged%20Feedback.png)

<br>

### 2. Envoyer un message de test pour générer une requête.

![img](../img-au-cas-ou/Forged%20Feedback2.png)

<br>

### 3. Intercepter la requête du feedback avec Burp Suite après l’envoi.

![img](../img-au-cas-ou/Forged%20Feedback3.png)

<br>

### 4. Modifier l’ID utilisateur dans le champ de l’objet JSON de la requête interceptée, puis envoyer.

![img](../img-au-cas-ou/Forged%20Feedback4.png)

<br>

### 5. Retourner sur le site pour constater que vous avez reussi la tache.

![img](../img-au-cas-ou/Forged%20Feedback5.png)