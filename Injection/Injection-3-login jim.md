# Injection - 3 - login-jim

## Outil utilisé

* aucun

## Méthodologie

Je me suis connecté en tant qu’administrateur via le bypass, puis je suis allé dans l’administration pour récupérer l’email de Jim. Ensuite, je me suis déconnecté de la session administrateur bypassée, j’ai renseigné l’email de Jim, puis j’ai bypassé le mot de passe.


## Vulnérabilité

* La connexion est vulnérable à une **injection SQL**
* C’est une faille **grave**

## Risques

* Connexion à n’importe quel compte
* Accès à des données sensibles

## Action

* Vérifier les entrées utilisateur
* Utiliser des requêtes préparées
* Renforcer la sécurité de la connexion
