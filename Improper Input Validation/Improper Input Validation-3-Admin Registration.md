# Admin Registration

## Méthodologie
J’ai intercepté la requête d’inscription avec Burp Suite lors de la création d’un nouveau compte.
En analysant les données envoyées au serveur, j’ai remarqué la présence d’un champ indiquant le rôle de l’utilisateur.
J’ai modifié ce champ pour définir le rôle sur `admin` avant d’envoyer la requête.
Le serveur n’effectuant aucune vérification côté backend, le compte a été créé avec des privilèges administrateur.

## Vulnérabilité
L’application fait confiance aux données envoyées par le client lors de l’inscription.
Il est possible de modifier le rôle utilisateur directement dans la requête sans contrôle serveur.

## Risques
- Création de comptes administrateurs non autorisés
- Accès complet aux fonctionnalités sensibles
- Compromission totale de l’application

## Recommandations
- Ne jamais permettre la définition des rôles côté client
- Vérifier et forcer les rôles côté serveur
- Restreindre strictement les privilèges administrateur
