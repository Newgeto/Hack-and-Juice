# Broken Authentication - 3 - reset jim's password

## Méthodologie

J'ai ouvert Burp Suite et j'ai config le proxy pour intercepter le trafic
puis j'ai émis un feedback normal via le navigateur et capturer la requête dans Burp.
Puis j'ai utiliser le Repeater  pour renvoyer la même requête plusieurs fois rapidement
et ça m'a valider le Flag.

## Vulnérabilité

Le formulaire de feedback ne vérifie pas si c'est un humain ou un robot qui envoie les requêtes. En interceptant une requête avec Burp Suite et en spammant le bouton "Send", on peut soumettre des dizaines de feedbacks automatiquement sans aucune restriction.

## Risques

* Pollution de la base de données avec des milliers de faux feedbacks
* Surcharge du serveur qui peut ralentir ou planter le site
* Les vrais avis clients deviennent inexploitables, noyés dans le spam

## Recommandations

* Ajouter un CAPTCHA pour bloquer les robots et scripts automatisés.
* Limiter le nombre de soumissions par IP/session.
* Détecter et bloquer les patterns suspects (multiples requêtes identiques en quelques secondes)