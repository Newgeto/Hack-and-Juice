# Improper Input Validation - 3 - Delux Fraud

## Outil utilisé

* **Inspection du navigateur firefox** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

J’ai créé un compte vierge et je suis allé dans **Membership** pour souscrire à l’abonnement mais je n’avais pas d’argent pour cliquer sur le bouton, j’ai donc inspecté ses propriétés et supprimé l’attribut **disabled** et la classe puis le bouton est devenu cliquable mais ca ne redirigais vers rien, suite a ca j’ai intercepté une requête **POST** contenant `paymentMethod: "wallet"` j’ai supprimé `"wallet"` laissé le champ vide et envoyé.


## Vulnérabilité

* Le serveur ne vérifie pas correctement le paiement et accepte n’importe quelle valeur envoyée par le client

## Risques

* Obtenir un abonnement sans payer

## Action

* Vérifier le paiement côté serveur avant d’accorder l’accès

## Étapes

### 1. Aller sur le site puis cliquer sur login.

![img](../img-au-cas-ou/Delux%20Fraud.png)

<br>

### 2. Une fois dessus, cliquer sur no yet customers puis créer un compte utilisateur (mettez n'importe quoi tant que vous le retenez pour vous connecter).

![img](../img-au-cas-ou/Delux%20Fraud2.png)

<br>

### 3. Une fois connecté, aller sur l'onglet delux membership.

![img](../img-au-cas-ou/Delux%20Fraud3.png)

<br>

### 4. Une fois dessus, cliquer sur le bouton au milieu de la page.

![img](../img-au-cas-ou/Delux%20Fraud4.png)

<br>

### 5. Après, vous allez devoir utiliser l'outil d'inspection de votre navigateur et soit repérer où est le code du bouton payer, ou sinon vous pouvez le trouver directement en cliquant dessus avec l'examinateur.

![img](../img-au-cas-ou/Delux%20Fraud5.png)

<br>

### 6. Une fois que vous avez trouvé la ligne de code du bouton, vous devrez supprimer les attributs `disabled` et `class` pour le rendre cliquable, malgré que vous n'avez pas d'argent bande de pauvre.

avant  
![img](../img-au-cas-ou/Delux%20Fraud6.png)

après  
![img](../img-au-cas-ou/Delux%20Fraud7.png)

<br>

### 7. Une fois que vous avez supprimé le code, le bouton est désormais cliquable. Vous cliquez dessus puis vous vous rendez sur burp.

![img](../img-au-cas-ou/Delux%20Fraudspebut.png)

<br>

### 8. Une fois sur burp, trouver la requête qui est `POST /rest/deluxe-membership HTTP/2`.

![img](../img-au-cas-ou/Delux%20Fraud8.png)
<br>

### 9. Modifier le contenu dans l'objet JSON de la requête, à la place de wallet vous mettez rien puis vous envoyez.

![img](../img-au-cas-ou/Delux%20Fraud9.png)

<br>

### 10. Retourner sur le site pour constater que vous avez réussi la tâche.

![img](../img-au-cas-ou/Delux%20Fraud10.png)



