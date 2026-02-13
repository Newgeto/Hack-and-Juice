# Improper Input Validation - 3 - Payback Time

## Outil utilisé

* **Burp Suite Community** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

J'ai ajouté des articles dans mon panier puis j'ai modifié la requête en mettant un nombre négatif et envoyé en méthode PUT, le site s'est actualisé avec cette modification j'ai ensuite validé l'achat jusqu'à la fin et au lieu de payer cela m'a crédité de l'argent.

## Vulnérabilité

* L'application accepte des quantités négatives sans vérification, ce qui inverse le sens du paiement

## Risques

* Gain d'argent illimité

## Recommandations

* Vérifier que les quantités sont positives côté serveur

## Étapes

### 1. Ajouter un article à votre panier, puis accéder au panier

![img](../img-au-cas-ou/Payback%20Time.png)

<br>

### 2. Une fois sur le panier, multiplier le nombre de l’article en x2 ou comme vous voulez, puis rendez‑vous sur Burp Suite

![img](../img-au-cas-ou/Payback%20Time2.png)

<br>

### 3. Une fois dans Burp Suite, vous devez chercher la requête `PUT /api/BasketItems/10`

![img](../img-au-cas-ou/Payback%20Time3.png)

<br>

### 4. Une fois que vous l’avez trouvée, vous modifiez le champ **quantité** dans l’objet JSON de la requête

![img](../img-au-cas-ou/Payback%20Time4.png)

<br>

### 5. Vous mettez un nombre négatif, par exemple `-111111111`, au lieu du nombre de base, puis vous envoyez

![img](../img-au-cas-ou/Payback%20Time5.png)

<br>

### 6. Ensuite, vous retournez sur le site et vous rafraîchissez, puis vous verrez que le nombre de l’article changera en `-1111111` et vous validez tout après le processus de paiement jusqu’à tomber sur la page où vous payez finalement

![img](../img-au-cas-ou/Payback%20Time6.png)

<br>

### 7. Une fois sur cette page, vous validez le paiement

![img](../img-au-cas-ou/Payback%20Time7.png)

<br>

### 8. Retournez sur le site pour constater que vous avez réussi la tâche

![img](../img-au-cas-ou/Payback%20Time8.png)
