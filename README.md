# Mon livre de recettes

Application web autonome (aucun serveur à gérer). Les recettes et les photos sont stockées dans le
navigateur de l'appareil, et, si la synchronisation est activée, dans un dépôt GitHub **privé** qui
vous appartient, pour les retrouver sur l'ordinateur et le téléphone.

## Synchronisation entre appareils (v2.0)

1. Sur github.com, créez un dépôt **privé** vide, par exemple `boite-a-recettes-donnees`.
2. Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token :
   expiration « No expiration » (ou la plus longue), accès limité à ce dépôt, permission
   *Contents : Read and write*.
3. Dans l'app : Réglages → Synchronisation → compte, dépôt, jeton → « Connecter et envoyer mes recettes ».
   Répétez l'étape 3 sur chaque appareil (le jeton reste dans le navigateur, il n'est jamais mis en ligne).

Chaque modification est envoyée automatiquement ; l'app récupère les nouveautés à l'ouverture, au retour
en avant-plan et toutes les cinq minutes. Hors ligne, les changements attendent la reconnexion.
Si deux appareils modifient la même recette hors ligne, la dernière version envoyée gagne.

## Héberger sur GitHub Pages

1. Crée un dépôt (ex. `livre-recettes`) et dépose ces fichiers à la racine :
   `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`.
2. Dans le dépôt : Settings → Pages → Source : « Deploy from a branch », branche `main`, dossier `/ (root)`.
3. Après une minute, l'app est disponible à `https://<ton-compte>.github.io/livre-recettes/`.

## Sur le téléphone

- Ouvre l'adresse dans Safari (iPhone) ou Chrome (Android), puis « Ajouter à l'écran d'accueil ».
  L'app s'ouvre alors en plein écran, fonctionne hors ligne, et « Prendre une photo » ouvre l'appareil photo.
- Les données restent dans ce navigateur. Utilise le bouton « Sauvegarder » (JSON) pour transférer
  le livre vers un autre appareil, puis « Restaurer » sur celui-ci.

## Mettre à jour

Remplace `index.html` **et** `sw.js` dans le dépôt : le nom du cache dans `sw.js` change à chaque version,
ce qui force le navigateur à charger la nouvelle version (sinon ferme et rouvre l'app deux fois).
