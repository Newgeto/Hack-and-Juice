# Injection - 3 - Login Admin

## Outil utilisé

* aucun

## Méthodologie

J’ai d’abord trouvé l’email de l’administrateur (`admin@juice-sh.op`) via les articles du site, puis j’ai saisi `' OR 1=1--` dans le champ mot de passe afin de couper la requête SQL, ce qui m’a permis de me connecter sans connaître le véritable mot de passe.


## Vulnérabilité

* La connexion est vulnérable à une **injection SQL**
* C'est une faille **critique**

## Risques

* Connexion à n'importe quel compte
* Accès administrateur complet
* Exposition de données sensibles

## Action

* Vérifier les entrées utilisateur
* Utiliser des requêtes préparées
* Renforcer la sécurité de la connexion
