# 🔩 Spécifications Matériel

Ce document sert à répertorier tout le matériel physique présent dans la borne d'origine ainsi que les pièces ajoutées.

---

## 📺 Écran Cathodique (CRT)

L'écran d'une vraie borne d'arcade est un élément précieux mais délicat.

*   **Marque & Modèle du Tube** : Videocolor 25" (Référence : `A59ECY13X01`)
*   **Modèle du Châssis (Platine électronique)** : Probablement **Hantarex Polo 25"** ou **Hantarex MTC 9110** (15kHz)
    *   *Comment identifier le châssis ?* : Regarde la couleur de la carte électronique et les inscriptions (souvent sérigraphiées sur le circuit imprimé ou sur les dissipateurs métalliques en aluminium). Le MTC 9110 possède un ventilateur de refroidissement dédié à côté du transformateur THT.
*   **Alimentation du Moniteur** :
    *   *Attention* : Si c'est un Hantarex MTC 9110, il nécessite **128V AC** (et 220V AC pour la démagnétisation/ventilateur) fournis par un transformateur d'isolement (ex: Hantarex US250/US300). Si c'est un Hantarex Polo 25", il s'alimente généralement directement en **230V AC** (mais nécessite tout de même un transformateur d'isolement interne pour la sécurité et éliminer les boucles de masse). **À vérifier impérativement avant mise sous tension.**
*   **Fréquence de balayage** : 15.625 kHz (Standard Arcade).

---

## ⚡ Alimentation Générale

*   **Alimentation Arcade d'origine** : (ex: Hantarex US250, alimentation à découpage d'origine)
    *   Sert à alimenter le peigne JAMMA en +5V et +12V.
*   **Alimentation du Raspberry Pi 5** :
    *   Alimentation USB-C officielle RPi 27W (5V / 5A), ou via la carte d'interface JAMMA si celle-ci gère l'alimentation du Pi à partir du +5V/+12V de la borne (avec un ampérage suffisant).

---

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

