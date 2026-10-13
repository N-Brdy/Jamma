# Matériel, inventaire et budget

Ce document répertorie le matériel de la borne, le matériel ajouté, l'état de ce
qui est reçu et ce qui reste à acheter. Il se complète en
[mission 1](../docs/parcours.md#mission-1--rassembler-le-matériel).

<a id="inventaire"></a>

## Inventaire

Statuts : `reçu` (récupéré / en main) · `en carton` (en ta possession, à retrouver)
· `à acheter` · `en stock`.

| Élément | Rôle | Statut | Emplacement |
| --- | --- | --- | --- |
| **Raspberry Pi 5** | Fait tourner Recalbox | en carton | À retrouver (mission 1) |
| **Recalbox RGB JAMMA 2** (HAT + boîtier) | Sortie vidéo 15 kHz, audio, JAMMA | reçu | |
| **Alimentation USB-C officielle (27 W / 5 A)** | Alimente le Pi | reçu | |
| **Carte microSD** (High Endurance conseillée) | Système Recalbox | reçu | |
| **2 × Joysticks Sanwa JLF-TP-8YT** | Manettes du panel | reçu | |
| **12 × Boutons Sanwa OBSF-30** | 6 boutons de jeu par joueur | reçu | |
| **4 × Boutons Sanwa OBSF-24** | Start 1P/2P et Select/Crédit | reçu | |
| **Fer à souder + multimètre** | Réparation et mesures | reçu | |
| **Filament d'impression 3D (PLA/PETG)** | Supports et boîtier | en stock | |
| **Plaque PMMA / MDF (3 à 5 mm)** | Plaque supérieure du panel | à acheter | |
| **Câble kick harness** | Boutons 4 à 6 par joueur | à acheter | |
| **Bandeau LED 12 V** | Remplace le néon du marquee | à acheter | |

## Budget

| Catégorie | Estimé | Réel |
| :--- | :--- | :--- |
| Électronique & cœur (Pi 5, alim, microSD) | 115 € | à compléter |
| Vidéo & connectique (HAT Recalbox RGB JAMMA 2) | 140 € | à compléter |
| Contrôles (Sanwa, plaque, filament) | 105 € | à compléter |
| Alimentation & câbles (kick harness) | 20 € | à compléter |
| Esthétique & finitions (LED marquee) | 20 € | à compléter |
| **TOTAL** | **~400 €** | **à compléter** |

## Contrôles à réception

À faire une fois le matériel rassemblé (mission 1).

- [ ] Le Raspberry Pi 5 démarre (voyant d'alimentation, écran HDMI sur la TV).
- [ ] Le HAT Recalbox RGB JAMMA 2 s'enfiche correctement sur le Pi.
- [ ] Le boîtier de protection protège la carte sans forcer.
- [ ] La microSD est lisible et accepte l'image Recalbox.
- [ ] L'alimentation officielle correspond bien au Pi 5 (5 V / 5 A).
- [ ] Les joysticks et boutons sont complets (ressorts, cosses, microswitchs).

## Fiche technique de la borne

### Écran cathodique (CRT)

- **Modèle du châssis :** **Hantarex Polo 25"** (15 kHz), confirmé par les photos
  (platine de cou et télécommande OC 03).
- **État :** platine principale et platine de cou très poussiéreuses mais
  physiquement intactes. La **télécommande OC 03** présente une **résistance R403
  brûlée** sous la diode D401.
- **Composants à contrôler/remplacer sur la télécommande (mission 5) :**
  - **R403** : résistance à couche métallique 0,5 W ou 1 W, valeur **1 kΩ**
    (ou 1,8 kΩ selon la révision du châssis).
  - **D401** : diode **BA159**, à tester au multimètre (probablement en court-circuit).
  - **C401** : condensateur **1 µF / 100 V**, à remplacer préventivement.
- **Fréquence de balayage :** 15,625 kHz (standard arcade).
- **Alimentation :** 230 V AC, **impérativement via le transformateur
  d'isolement** (le gros bloc métallique à gauche) pour éviter les électrocutions
  et les boucles de masse.

### Alimentation générale

- **Alimentation arcade d'origine** (ex. Hantarex US250, à confirmer) : alimente
  le peigne JAMMA en +5 V et +12 V.
- **Alimentation du Raspberry Pi 5** : USB-C officielle 27 W (5 V / 5 A), ou via
  la carte d'interface JAMMA si elle fournit un ampérage suffisant.

### Contrôles (panel)

- **Fabrication :** sur-mesure — plaque supérieure découpée au laser, supports
  imprimés en 3D sur la Prusa Core One.
- **Joysticks :** Sanwa JLF-TP-8YT.
- **Boutons :** Sanwa OBSF-30 (30 mm) et OBSF-24 (24 mm).
- **Configuration :** 6 boutons par joueur (indispensable pour Street Fighter II),
  Start 1P/2P, crédit via le monnayeur d'origine sur le peigne JAMMA.

## Contrôles avant branchement sur le CRT

À faire avant la mission 7 (voir la [règle d'or](../docs/configuration.md#signal-vidéo)).

- [ ] Recalbox détecte le HAT Recalbox RGB JAMMA 2.
- [ ] Le signal de sortie est bien en 15 kHz analogique.
- [ ] Le peigne JAMMA bleu est relié : rouge, vert, bleu, synchro, masse.
- [ ] Le transformateur d'isolement alimente le moniteur.
- [ ] Aucun condensateur gonflé ni trace noircie sur le châssis.
- [ ] La borne est **débranchée** pendant le branchement du peigne.

## Raccordement prévu

- **Solution retenue :** **Recalbox RGB JAMMA 2**, conçue pour le Raspberry Pi 5 et
  s'enfichant directement sur le peigne JAMMA.
- **Vidéo :** RPi 5 → GPIO → HAT RGB JAMMA 2 → peigne JAMMA (RVB, synchro, masse) →
  châssis Hantarex.
- **Boutons 4 à 6 (kick harness) :** reliés au connecteur prévu sur le HAT, ou aux
  broches libres du peigne (mission 13).
- **Audio :** amplificateur intégré au HAT → peigne JAMMA → haut-parleur de la borne.

## À acheter

- Câble **kick harness** (boutons 4 à 6 par joueur) — pour la mission 13.
- **Plaque PMMA / MDF** 3 à 5 mm pour le panel — pour la mission 12.
- **Bandeau LED 12 V** pour le marquee — pour la mission 15.
