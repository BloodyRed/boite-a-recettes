# Mon livre de recettes

Application web autonome (aucun serveur, aucune dépendance à installer). Les recettes et les photos
sont stockées dans le navigateur (IndexedDB) de l'appareil qui l'utilise.

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

Remplace `index.html` dans le dépôt. Si l'ancienne version reste affichée, change `livre-recettes-v1`
en `v2` dans `sw.js` (ou ferme et rouvre l'app deux fois).