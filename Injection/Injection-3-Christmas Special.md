# Injection - 3 - Christmas Special

## Outil utilisé

* **Burp Suite Community** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

J’ai utilisé le dump de la base de données d’un défi précédent (schema database) pour chercher le mot Christmas dans la table des produits, ce qui m’a permis de trouver un produit caché avec l’ID 10. Ensuite, je me suis connecté avec un compte utilisateur, j’ai ajouté un produit au panier, puis j’ai intercepté la requête avec Burp. J’ai modifié le champ ProductId en mettant 10 et envoyé la requête, le produit spécial s’est alors ajouté au panier.

## Vulnérabilité

* L'application ne vérifie pas si un produit est visible ou disponible avant de l'ajouter au panier

## Risque

* Accès et commande de produits cachés ou archivés non autorisés

## Action

* Valider côté serveur que le produit existe, est disponible et non supprimé avant l'ajout au panier