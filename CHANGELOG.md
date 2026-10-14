# Questionnaire financier Prestaterre — V0.56

## Numéro d'opération SIAP : un seul par opération
- Les champs SIAP ligne par ligne de la V0.55 sont remplacés par **un champ unique « Numéro d'opération SIAP »** (facultatif), en fin de questionnaire (étape 6).
- Il n'apparaît que si l'opération mobilise un financement agréé dans SIAP : aides à la pierre (PLAI, PLAI adapté, PLUS, bonus, surcharge foncière, Palulos) ou prêts PLAI, PLUS, PLS, PSLA. Les aides concernées sont rappelées à côté du champ.
- Le numéro est rattaché à l'opération : JSON `operation.numeroSIAP`, encadré « Résumé opération » de l'étape 6 et du bilan PDF, colonne « N° SIAP » du CSV des aides pour les lignes concernées.
- Une modification du numéro après envoi fait passer l'opération en « Modifiée après envoi ».
- Les numéros saisis ligne par ligne en V0.55 sont repris automatiquement dans le champ unique.

---

# Questionnaire financier Prestaterre — V0.55

## Alignement des champs (toutes les étapes)
- Hauteur unique de 44 px pour tous les champs et menus des formulaires, avec la même taille de texte partout.
- Dans une même ligne, les champs sont alignés même quand les libellés sont de longueurs différentes (icône (i) de l'étape 1, libellés sur deux lignes).
- Étape 1 : les trois champs ont retrouvé la même largeur. Une règle de mise en page des aides (V0.53) les déformait. Le bouton natif « Choisir un fichier » est masqué : toute la zone de dépôt est cliquable.
- Étape 5 : chaque carte d'aide suit la même grille de colonnes. Catégorie / unité, aide / montant et statut / commentaire sont alignés d'une carte à l'autre, et le résultat calculé est toujours à la même place.
- Bilan PDF : les libellés en gras ne débordent plus sur la colonne voisine.

## Catalogue des aides (40 dispositifs)
- **Fonds européens détaillés** : FEDER, FTJ, FEADER, ELENA, LIFE, autre fonds (Interreg, FSE+…).
- **Aides à la pierre détaillées** : subvention PLAI, prime PLAI adapté, subvention PLUS du délégataire, bonus (petits logements, recyclage foncier, transformation de bureaux), surcharge foncière, Palulos / rénovation énergétique.
- **Prêts du logement social détaillés** : PLAI, PLUS, PLS, PSLA, PLI, Gaïa / BRS.
- **CAF et ARS retirées.** Les brouillons qui les contenaient sont repris en « Autre dispositif », avec leur nom.

- **Subventions** : FEDER – Fonds européen de développement régional · FTJ – Fonds pour une transition juste · FEADER – développement rural (LEADER) · ELENA – assistance technique (BEI) · Programme LIFE (transition énergétique propre) · Autre fonds européen (Interreg, FSE+…) · Aides à la pierre – subvention PLAI *(SIAP)* · Aides à la pierre – prime PLAI adapté *(SIAP)* · Aides à la pierre – subvention PLUS (délégataire) *(SIAP)* · Aides à la pierre – bonus (petits logements, recyclage foncier, transformation de bureaux…) *(SIAP)* · Aides à la pierre – subvention pour surcharge foncière *(SIAP)* · Aides à la pierre – Palulos / rénovation énergétique *(SIAP)* · Fonds vert · Anah (MaPrimeRénov’ Copropriété…) · ANRU – renouvellement urbain (NPNRU) · Fonds Chaleur (ADEME) · Agence de l’eau · Région · Département · Métropole / EPCI / commune · Action Logement – subvention
- **Primes énergie (CEE)** : Certificats d’économies d’énergie (CEE, Coup de pouce…)
- **Prêts aidés et bonifiés** : Éco-prêt logement social · Prêt Adaptéo (chauffage décarboné) · Prêt PLAI – prêt locatif aidé d’intégration (dont PLAI adapté, PLAI RO ANRU) *(SIAP)* · Prêt PLUS – prêt locatif à usage social (dont PLUS Constructions vertes) *(SIAP)* · Prêt PLS – prêt locatif social *(SIAP)* · Prêt PSLA – location-accession *(SIAP)* · Prêt PLI – logement intermédiaire · Prêt Gaïa / BRS – foncier en bail réel solidaire · Autres prêts Banque des Territoires (PAM, PHB 2.0, Intracting…) · Prêt vert bancaire (banques, Bpifrance) · Action Logement – prêt
- **Avantages fiscaux** : Exonération ou abattement de TFPB · TVA à taux réduit (5,5 % ou 10 %)
- **Contrats de performance et tiers-financement** : Contrat de performance énergétique (CPE) · Tiers-financement (CPE tiers-financé, société de tiers-financement)
- **Recettes et valorisation** : Marges locales bonifiées – majoration de loyer · Label bas-carbone – crédits carbone · Photovoltaïque – revente ou autoconsommation

## Nombre de logements par aide
En mode « € / logt », chaque aide a son propre nombre de logements concernés (par exemple 14 PLAI sur 48 logements). S'il n'est pas renseigné, le nombre total de logements de l'opération s'applique.

## Numéros SIAP (facultatif, en fin de questionnaire)
Dès qu'une aide agréée dans SIAP est saisie, l'étape 6 propose un champ « N° d'opération SIAP » pour cette ligne : aides à la pierre, prêts PLAI, PLUS, PLS ou PSLA. PLI et Gaïa / BRS n'en ont pas, car ils ne passent pas par SIAP. Le numéro figure dans le tableau des aides (étape 6 et PDF), dans le CSV des aides (colonne « N° SIAP ») et dans le JSON (`numerosSIAP`).

## Contrôles
Tests Chromium (CSP + SRI actives) : catalogue, calcul par logement, SIAP, marges locales, persistance, reprise des anciens brouillons (V0.52 à V0.54), ZIP, PDF. Non-régression V0.50 à V0.54 : OK.
