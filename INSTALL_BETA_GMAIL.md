# Installation V0.56 — GitHub Pages

1. Remplacer l'ancien `index.html` par celui de la V0.56.
2. Publier normalement via GitHub Pages.
3. Au premier chargement, faire un rechargement forcé (`Cmd + Shift + R` sur Mac ou `Ctrl + F5` sur Windows).

Les brouillons créés en V0.49 à V0.55 sont repris tels quels.

## Brouillons
Les données restent locales au navigateur : IndexedDB contient l'état complet et les documents dans les limites prévues, avec localStorage en secours. Le bouton `Sauvegarder brouillon` exporte un `.ptdraft` portable réimportable depuis l'écran `Mes opérations`.

Une donnée financière validée n'est supprimée que par le bouton × du récapitulatif.

## Envoi (unitaire ou groupé)
Depuis l'étape 6 ou depuis `Mes opérations` > `Envoyer par mail`, le ZIP est téléchargé localement puis la messagerie s'ouvre ; il reste à joindre le ZIP au message.

Après envoi, l'opération est marquée **Déjà envoyée** : sa tuile est grisée et elle n'est plus cochable dans l'envoi groupé. Pour la corriger, cliquer sur l'icône crayon de la tuile ; un avertissement rappelle que le dossier devra être renvoyé.
