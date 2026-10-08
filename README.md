# Fusion PDF gratuite locale

Outil gratuit pour fusionner plusieurs fichiers PDF en un seul, directement dans le navigateur.

## Utilisation

1. Téléchargez `Fusion-PDF.html`.
2. Double-cliquez dessus pour l'ouvrir dans Chrome, Edge, Firefox ou Safari.
3. Glissez-déposez vos PDF, ou cliquez sur la zone pour les choisir.
4. Réorganisez-les (glisser-déposer des lignes ou flèches haut/bas), nommez le fichier final, puis cliquez sur « Fusionner et télécharger ».

## Confidentialité

Le traitement est 100 % local : les PDF ne quittent jamais votre ordinateur, aucun serveur, aucun suivi.
La bibliothèque [pdf-lib](https://pdf-lib.js.org/) 1.17.1 (licence MIT) est intégrée au fichier, qui fonctionne donc hors ligne.

## Choix de sécurité

- Les noms de fichiers sont affichés avec `textContent` (jamais en HTML), ce qui évite toute injection.
- Aucune donnée n'est envoyée sur le réseau et rien n'est stocké. Une règle CSP (balise `meta`) l'impose au navigateur : `connect-src 'none'` interdit tout envoi, `default-src 'none'` bloque tout le reste, seules les polices Google sont autorisées au chargement.
- La CSP autorise `'unsafe-inline'` pour le script et le style, parce que tout le code est dans le fichier HTML. À durcir (nonce ou fichiers séparés) si le JavaScript est un jour déplacé hors du fichier.
- Les PDF protégés par mot de passe ou illisibles sont signalés et ignorés.

Les règles de développement du projet sont décrites dans `CLAUDE.md`.
