# XSS - 3 - Client-side XSS Protection

## Outil utilisé

* **Burp Suite Community** utilisé pour intercepter et analyser les requêtes HTTP

## Méthodologie

J’ai créé un compte sur le site avant de valider j’ai activé l’interception sur Burp puis j’ai soumis le formulaire ce qui a envoyé la requête sans valider réellement sur le site ensuite j’ai injecté la requête XSS dans le champ email de la requête puis je l’ai envoyée en désactivant l’interception.

## Vulnérabilité

* L'API accepte du code malveillant sans validation et le stocke en base de données

## Risques

* vol de sessions utilisateurs

## Recommandations

* valider et échapper les données côté serveur

## Image

![Image 1](https://files.catbox.moe/dwjizz.png)

![Image 2](https://files.catbox.moe/jgk8re.png)