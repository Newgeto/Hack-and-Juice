# Broken Access Control - Level 3 - Manipulate Basket

## Outil utilisé

* **Burp Suite Community** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

J'ai intercepté avec Burp Suite la requête quand j'ajoute un produit à mon panier, j'ai changé le `BasketId` pour mettre l'ID d'un autre utilisateur, puis j'ai envoyé la requête modifiée.

## Vulnérabilité

* Pas de vérification que le panier appartient bien à l'utilisateur

## Risques

* N'importe qui peut ajouter des produits dans le panier des autres et manipuler les commandes des victimes

## Action

* Vérifier que l'utilisateur accède uniquement à son propre panier
* Bloquer les modifications d'ID de panier

## Étapes

### 1. Ajouter un article à votre panier, puis accéder au panier

![img](../img-au-cas-ou/Manipulate%20Basket.png)

<br>

### 2. Une fois sur le panier, ouvrir Burp Suite (recommandé) ou utiliser l’inspecteur du navigateur, aller dans l’onglet Network et intercepter la requête `POST /api/BasketItems/`

![img](../img-au-cas-ou/Manipulate%20Basket2.png)

<br>

### 3. Une fois dans Burp Suite, vous avez intercepté la requête `POST /api/BasketItems/`

![img](../img-au-cas-ou/Manipulate%20Basket3.png)

<br>

### 4. Une fois la requête interceptée, la modifier en ajoutant un deuxième `basketId` avec un autre identifiant (par exemple `3`)

![img](../img-au-cas-ou/Manipulate%20Basket4.png)

<br>

### 5. Retourner sur le site pour constater que la tâche a été réussie

![img](../img-au-cas-ou/Manipulate%20Basket5.png)
