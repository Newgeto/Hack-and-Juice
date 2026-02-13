# Product Tampering – OWASP SSL Advanced Forensic Tool

## Méthodologie
J’ai ouvert la page du produit **OWASP SSL Advanced Forensic Tool (O-Saft)** dans l’application.
Ensuite, j’ai utilisé les outils développeur du navigateur pour inspecter le code HTML de la page.
J’ai localisé le lien présent dans la description du produit (`href`).
J’ai modifié manuellement la valeur du lien pour la remplacer par l’URL demandée : `https://owasp.slack.com`.
Une fois la modification appliquée, le challenge a été validé.

## Vulnérabilité
Le contenu affiché côté client peut être modifié directement via le navigateur.
L’application ne vérifie pas l’intégrité des données affichées ou modifiées côté client.

## Risques
- Modification du contenu des produits
- Redirection vers des sites non prévus
- Tromperie des utilisateurs
- Atteinte à la crédibilité de l’application

## Recommandations
- Vérifier l’intégrité des données côté serveur
- Ne pas faire confiance aux modifications côté client
- Protéger les éléments sensibles contre la manipulation
