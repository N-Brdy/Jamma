# 🔩 Spécifications Matériel

Ce document sert à répertorier tout le matériel physique présent dans la borne d'origine ainsi que les pièces ajoutées.

---

## 📺 Écran Cathodique (CRT)

L'écran d'une vraie borne d'arcade est un élément précieux mais délicat.

*   **Modèle du Châssis (Platine électronique)** : **Hantarex Polo 25"** (15kHz) - *Confirmé par les photos (platine de cou et télécommande OC 03)*.
    *   *Constructeur du Châssis* : HANTAREX (Florence, Italie - Via P. Ricasoli 76/78). La platine électronique est fixée verticalement sur le côté droit intérieur de la borne. La tétine THT (câble rouge) est connectée à l'anode du tube.
    *   *Tube Cathodique* : Tube Videocolor de référence **A59ECY13X01** (diagonale d'environ 59 cm / 25 pouces). Numéro de série/lot : **I105583**.
    *   *État visuel* : La platine principale et la platine de cou (neck board) sont très poussiéreuses mais semblent physiquement intactes. En revanche, **la télécommande de réglages déportée (PCB OC 03) présente une résistance R403 complètement brûlée/carbonisée** juste sous la diode D401.
    *   *Composants à vérifier/remplacer sur cette télécommande* :
        *   **R403** (Résistance) : Complètement brûlée, valeur d'origine de **1kΩ** (ou **1.8kΩ** selon la révision du châssis, à remplacer par une résistance de même valeur, de préférence à couche métallique 0.5W ou 1W).
        *   **D401** (Diode BA159) : À tester au multimètre, elle est probablement en court-circuit ou a souffert.
        *   **C401** (Condensateur 1µF / 100V) : À remplacer préventivement (un condensateur fatigué ou en court-circuit dans cette zone peut causer la surchauffe).
*   **Alimentation du Moniteur** :
    *   Le Hantarex Polo 25" nécessite du **230V AC**. Il doit impérativement être alimenté à travers le **transformateur d'isolement** (le gros transformateur lourd métallique visible à gauche de l'alimentation à découpage sur les photos) pour éviter les électrocutions (châssis sous tension) et les boucles de masse.
*   **Fréquence de balayage** : 15.625 kHz (Standard Arcade).

---

## ⚡ Alimentation Générale

*   **Alimentation Arcade d'origine** : **Kiesewetter** (bloc d'alimentation à découpage métallique).
    *   *Borniers identifiés* : `AC1`, `AC2` (Entrée secteur), `FG` (Terre), `+12V`, `-12V`, `-5V`, `G` (Masse/GND), `+5V`, `+5V`, et `ADJ` (potentiomètre d'ajustement fin de la tension +5V).
    *   *Fusibles de sécurité* : Deux fusibles en verre montés sur une petite platine en bois à côté du bloc d'alimentation.
*   **Alimentation du Raspberry Pi 5** :
    *   Alimentation USB-C officielle RPi 27W (5V / 5A), ou via la carte d'interface JAMMA si celle-ci gère l'alimentation du Pi à partir du +5V/+12V de la borne (avec un ampérage suffisant).

---

## 📦 Cabinet, Monnayeur & Boîtier de Répartition

*   **Identification du Meuble (Cabinet)** :
    *   *Constructeur / Exploitant* : **W WYSS & FILS SA** (Suisse), logo visible sur le marquee.
    *   *Esthétique* : Panneau inférieur imitant le bois ou le granit sombre.
    *   *Vitre d'écran* : Très empoussiérée avec des morceaux de ruban adhésif bleu (portant les inscriptions "3" et "S").
*   **Boîtier de Répartition (Platine métallique centrale)** :
    *   Sert de point de jonction avec indications en français :
        *   `DEMAGN.` (Démagnétisation / Degauss)
        *   `SON et HP` (Audio / Haut-parleurs)
        *   `PUPITRE` (Commandes joueurs)
        *   `ALIMENTATION`
        *   `RVB` (Signal vidéo vers le moniteur)
        *   `MONNAYEUR`
    *   *Indicateurs de Diagnostic* : Équipé de **trois voyants LED rouges** de diagnostic indiquant la présence des tensions **+5V**, **+12V** et **-5V**.
*   **Monnayeur (Coin Door)** :
    *   *Façade* : Porte métallique à trois fentes d'insertion de pièces.
    *   *Porte intérieure* : Numéro de série/identification **131610** inscrit au marqueur orange. Serrure à came batteuse en place.
    *   *Composant détaché* : Un gros boulon métallique a été trouvé au fond de la caisse, suggérant une pièce desserrée ou démontée lors de précédentes interventions.


## 🕹️ Contrôles (Panel)

*   **Fabrication du Panel** : Sur-mesure (découpe laser pour la plaque supérieure en acrylique/bois et pièces imprimées en 3D avec la Prusa Core One pour les supports et l'intégration).
*   **Type de Joysticks** : Sanwa JLF-TP-8YT (recommandé pour les jeux de combat/Street Fighter).
*   **Type de Boutons** : Sanwa OBSF-30 (boutons clipsables 30mm) ou OBSC-30 (translucides).
*   **Configuration du Panel** :
    *   Joueur 1 : `[x]` 6 boutons (Indispensable pour Street Fighter : Light/Medium/Heavy Punch & Kick).
    *   Joueur 2 : `[x]` 6 boutons (Indispensable pour Street Fighter).
    *   Bouton Crédit / Insert Coin : Via le monnayeur d'origine sur le peigne JAMMA ou boutons cachés sous le panel.
    *   Bouton Start 1P & 2P : Oui.

---

## 🔗 Raccordement (Le Pont entre le Pi et la Borne)

*   **Solution choisie** : **Recalbox RGB JAMMA 2** (recommandé car conçu spécifiquement pour le Raspberry Pi 5 et s'enfiche directement sur le peigne JAMMA bleu).
*   **Gestion des boutons additionnels (Kick Harness)** :
    *   Le standard JAMMA ne gère nativement que 3 à 4 boutons par joueur. Pour Street Fighter (6 boutons), les boutons 4, 5 et 6 seront raccordés soit via un câblage additionnel ("Kick Harness" branché sur le connecteur prévu sur la carte Recalbox RGB JAMMA 2), soit via les broches libres configurées sur le peigne JAMMA.
*   **Câblage vidéo** :
    *   De : RPi 5 -> GPIO -> Recalbox RGB JAMMA 2.
    *   Vers : Peigne JAMMA bleu (signaux Rouge, Vert, Bleu, Synchro, Masse) branché directement sur le châssis Hantarex.
*   **Câblage Audio** :
    *   Géré directement par la carte Recalbox RGB JAMMA 2 (amplificateur audio intégré qui envoie le son du Pi vers le peigne JAMMA pour alimenter le haut-parleur de la borne).

