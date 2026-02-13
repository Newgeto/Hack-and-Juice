# XSS - 3 - API-only XSS

## Outil utilisé

* **Burp Suite Community** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

J’ai repéré la requête après avoir ajouté un article au panier, la requête interceptée était en **PUT** sur `/api/BasketItems/9`, je l’ai ensuite modifiée en **GET** vers `/api/Products/1` en changeant l’en-tête afin de récupérer les informations du produit, j’ai copié la description du produit **ID 1**, puis j’y ai ajouté le payload **XSS**, enfin j’ai renvoyé la requête en **PUT** sur `/api/Products/1` pour enregistrer la modification.


## Vulnérabilité

L'API accepte du code malveillant sans validation et le stocke en base de données

## Risques

* vol de sessions utilisateurs

## Recommandations

* valider et échapper les données côté serveur

## Étapes

### 1. Sur le site, ajouter un article (par exemple le premier) au panier, puis aller sur Burp Suite.

![img](../img-au-cas-ou/API-only%20XSS.png)

<br>

### 2. Une fois le produit ajouté, dans Burp Suite, repérer une requête PUT ou GET (n’importe laquelle) et l’envoyer au Repeater.

![img](../img-au-cas-ou/API-only%20XSS2.png)

<br>

### 3. Dans le Repeater, modifier l’en-tête, par exemple de `GET /api/BasketItems/9` à `GET /api/Products/1`, afin d’obtenir les informations du produit 1, qui est le premier sur la page.

![img](../img-au-cas-ou/API-only%20XSS3.png)

<br>

### 4. Une fois les informations récupérées, copier-coller l’objet JSON et garder uniquement la description.

![img](../img-au-cas-ou/API-only%20XSS4.png)

<br>

### 5. Modifier la description avec le payload XSS suivant `<iframe src="javascript:alert(\`xss\`)">`, puis changer la méthode en PUT et ajouter `Content-Type: application/json` dans la requête.

![img](../img-au-cas-ou/API-only%20XSS5.png)

<br>

### 6. Retourner sur le site pour constater que la tâche a été réussie.

![img](../img-au-cas-ou/API-only%20XSS6.png)
