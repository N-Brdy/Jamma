# Projet Jamma - Rénovation Borne d'Arcade (Raspberry Pi 5 & Écran CRT Hantarex)

Bienvenue dans le dépôt de suivi pour la rénovation de ta borne d'arcade ! Ce projet vise à redonner vie à une borne d'époque équipée d'un écran cathodique Hantarex en y intégrant un Raspberry Pi 5.

## 📁 Structure du Projet

Voici l'organisation des fichiers pour suivre le projet pas à pas :

*   [README.md](README.md) : Vue d'ensemble et guide général (ce fichier).
*   [TODO.md](TODO.md) : Suivi des tâches classées par étapes (Châssis, Vidéo, Audio, Contrôles, Logiciel).
*   [specs_materiel.md](specs_materiel.md) : Fiche technique de la borne (type de Hantarex, câblage JAMMA ou autre, adaptateurs vidéo).
*   [configuration_logiciel.md](configuration_logiciel.md) : Commandes utiles, configuration du signal 15kHz du RPi5, émulateurs.
*   [liste_achats.md](liste_achats.md) : Liste du matériel nécessaire avec suivi du budget et des commandes.
*   [liste_jeux.md](liste_jeux.md) : Liste des jeux sélectionnés à installer et configurer.

---

## 🚀 Les Grandes Étapes de la Rénovation

Pour mener ce projet à bien sans se décourager ou abîmer le matériel d'époque (surtout le moniteur CRT haute tension !), nous te proposons la démarche suivante :

### Étape 1 : Inventaire et Sécurité (État des Lieux)
*   **Sécurité CRT** : Identification du modèle d'Hantarex et apprentissage des règles de sécurité (décharge du tube).
*   **Inventaire** : Vérifier ce qui fonctionne (alimentation d'origine, haut-parleurs, boutons, moniteur).
*   **Choix du raccordement** : Décider si l'on garde le câblage JAMMA d'origine (via une carte d'interface) ou si l'on refait le câblage à neuf (encodeurs USB).

### Étape 2 : L'Écran Cathodique (Le cœur de la borne)
*   **Signal 15kHz** : C'est le point critique. Les écrans Hantarex attendent un signal vidéo analogique spécifique (15kHz RVB/RGB). Le RPi5 sort du numérique (HDMI).
*   **Choix de l'interface vidéo** :
    *   *Option A (Recommandée - Direct JAMMA)* : Utiliser une carte chapeau (HAT) comme le **RGB-Pi JAMMA**, **Pi2JAMMA** ou **JammaPi** pour connecter le Pi directement sur le peigne JAMMA de la borne. Cela gère la vidéo 15kHz et les contrôles.
    *   *Option B (SCART/Péritel)* : Utiliser un câble RGB-Pi (SCART) vers un adaptateur châssis CRT.
    *   *Option C (VGA)* : Utiliser un HAT VGA (ex: Gert VGA666) puis un convertisseur VGA vers RGB Hantarex.
*   **Ajustements physiques** : Réglages des potards du châssis Hantarex (synchro, taille, position, couleurs).

### Étape 3 : Contrôles et Audio
*   **Contrôles** : Raccordement des joysticks et boutons (soudure sur le JAMMA ou câblage direct sur encodeur USB type XinMo/Brook, ou GPIO).
*   **Audio** : Amplification du signal sonore du Pi vers les haut-parleurs mono ou stéréo de la borne.

### Étape 4 : Système et Distribution (Logiciel)
*   **Système d'exploitation** : Choix de la distribution (Recalbox RGB Dual, Batocera, RGB-Pi OS, Retropie).
*   **Optimisation des jeux** : Configuration des "Pixel Perfect" résolutions pour que les jeux s'affichent dans leur résolution d'origine (ex: 240p/320x224 pour Neo-Geo).

### Étape 5 : Intégration Finale et Esthétique
*   **Montage propre** : Fixation du Pi, des alimentations et du câblage dans la borne.
*   **Finitions** : Bouton d'allumage général, ventilation, éclairage du marquee, nettoyage/restauration esthétique.
