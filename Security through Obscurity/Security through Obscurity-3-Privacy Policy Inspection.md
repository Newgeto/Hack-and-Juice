# Security through Obscurity-3-Privacy Policy Inspection

## Méthodologie
J’ai consulté la page de la politique de confidentialité puis inspecté le code source à l’aide des outils développeur.
En analysant le HTML, j’ai identifié plusieurs mots associés à la classe CSS `hot`.
En assemblant ces mots dans l’ordre, j’ai pu reconstituer une URL cachée permettant de valider le challenge, ce qui m'a donner "https://ctf.juice.cyber.epitest.eu/We/may/also/instruct/you/to/refuse/all/reasonably/necessary/responsibility


## Vulnérabilité
Des informations sensibles sont dissimulées directement dans le code HTML via des classes CSS.
Ces éléments sont invisibles pour l’utilisateur classique mais accessibles par inspection du code.

## Risques
- Divulgation d’informations cachées
- Accès à des ressources non prévues
- Contournement de mécanismes de sécurité

## Recommandations
- Ne pas cacher d’informations sensibles dans le code client
- Éviter la sécurité par l’obscurité
- Mettre en place des contrôles d’accès côté serveur
