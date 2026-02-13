# Sensitive Data Exposure -3-Login Amy

## Méthodologie
j'ai commencé par annalysé la question et cette partie m'a intéroger : "This could take 93.83 billion trillion trillion centuries to brute force, but luckily she did not read the "One Important Final Note". J'ai donc copier coller ça sur internet et je suis tomber sur ce site : "https://www.grc.com/haystack.htm?id=" dans la section "One important final note" il y a un exemple de mdp avec "D0g....................." j'ai donc essayer de brut force avec burp en gardant la même composition (1 lettre majuscule, 1 lettre, 1lettre minuscule, et 21 "."). Une fois le brutForce fait un trouve que sont mdp est "K1f....................."  

## Vulnérabilité
Amy a utiliser le même paterne de mdp que celui donner sur un site internet, une fois le site trouver et le lien fait, un simple brutforce suffit pour trouver son mdp

## Risques
- Compromission de compte
- Accès non autorisé
- Vol de données personnelles

## Recommandations
- Ne pas recopier un mdp d'un site internet
- Utiliser des mots de passe uniques
- Activer l’authentification à deux facteurs
