# Broken Authentication - 3 - GDPR Data Erasure

## Méthodologie
Comme pour le compte de Bender, j’ai récupéré l’adresse email de Chris depuis les articles du site internet.
J’ai ensuite ajouté une injection SQL (`' --`) dans le champ email, ce qui m’a permis de contourner l’authentification et de me connecter au compte de Chris sans connaître son mot de passe.

## Vulnérabilités
- Absence de protection contre les injections SQL
- Validation insuffisante des entrées utilisateur

## Risques
- Accès non autorisé aux comptes utilisateurs
- Suppression ou modification de données sensibles
- Non-respect du RGPD

## Recommandations
- Filtrer et sécuriser les entrées utilisateur
- Utiliser des requêtes préparées
- Renforcer les contrôles d’authentification
