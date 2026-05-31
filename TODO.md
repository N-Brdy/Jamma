# 📝 Suivi des Tâches (TODO)

Ce fichier regroupe toutes les tâches nécessaires à la réalisation de ta borne. Utilise-le pour cocher les cases au fur et à mesure.

---

## 🛡️ Phase 1 : Préparation, Électricité & Sécurité
- [ ] Inspecter visuellement l'intérieur de la borne (câblage existant, alimentation, peigne JAMMA bleu).
- [x] Identifier précisément le modèle de la platine Hantarex (confirmé : **Hantarex Polo 25"** grâce aux photos).
- [ ] Réparer la télécommande de réglages déportée (PCB OC 03) : remplacer la résistance R403 brûlée (1kΩ ou 1.8kΩ selon la révision), tester la diode D401 (BA159) et remplacer le condensateur C401 (1µF / 100V) préventivement.
- [ ] Vérifier minutieusement le sens et l'alignement du connecteur de la télécommande (J407) avant toute mise sous tension (un décalage de broches peut causer ce type de court-circuit).
- [ ] Inspecter le transformateur d'isolement (le gros bloc métallique à gauche de l'alimentation) pour s'assurer que l'écran sera alimenté avec la bonne tension et isolé du secteur.
- [ ] Dépoussiérer la platine principale du moniteur Polo et sa platine de cou (neck board) après avoir déchargé le tube cathodique en toute sécurité.
- [ ] Lire la documentation de sécurité pour savoir comment décharger un tube cathodique en toute sécurité (indispensable si tu dois démonter le châssis ou nettoyer en profondeur).

## 📐 Phase 2 : Conception & Fabrication du Panel sous Fusion 360 (Spécial Street Fighter)
- [ ] Concevoir le panel complet en 3D sur **Fusion 360** :
    - [ ] Dessiner l'esquisse 2D de la plaque supérieure avec les emplacements précis (diamètre 30mm pour les 12 boutons de jeu Sanwa, diamètre 24mm pour les 4 boutons Start/Select).
    - [ ] Choisir et implanter le layout des boutons (ex: layout Vewlix ou Sega Astro City).
    - [ ] Modéliser les supports de montage physiques pour fixer le panel sur le châssis en bois de la borne.
- [ ] Exporter l'esquisse de découpe sous format **DXF** depuis Fusion 360 pour la découpeuse laser.
- [ ] Découper un prototype rapide dans du carton ou du MDF fin (3mm) au laser pour valider l'ergonomie physique des boutons et sticks.
- [ ] Concevoir sous Fusion 360 et imprimer en 3D avec la **Prusa Core One** :
    - [ ] Les charnières, équerres ou supports de fixation du panel sur la borne.
    - [ ] Des bagues d'adaptation ou supports pour les joysticks Sanwa JLF.
    - [ ] Le support de fixation interne pour le Raspberry Pi 5 et son boîtier de protection.
- [ ] Découper la plaque finale (ex: PMMA/Plexiglas double épaisseur ou MDF peint).
- [ ] Assembler et monter les joysticks, microswitchs et boutons sur le panel final.

## 📺 Phase 3 : Vidéo & Intégration JAMMA (CRT 15kHz)
- [ ] Commander le matériel : Raspberry Pi 5, Recalbox RGB JAMMA 2 et les boutons/sticks Sanwa.
- [ ] Configurer la carte MicroSD avec la dernière version de **Recalbox (compatible Pi 5 / RGB JAMMA 2)**.
- [ ] Brancher le Recalbox RGB JAMMA 2 sur le Raspberry Pi 5 et l'installer dans son boîtier de protection.
- [ ] Raccorder le peigne JAMMA bleu sur la carte Recalbox RGB JAMMA 2.
- [ ] Mettre la borne sous tension pour tester si le moniteur CRT Hantarex s'allume et si l'image se synchronise correctement en 15kHz (écran d'accueil Recalbox).
- [ ] Ajuster la géométrie et les couleurs à l'aide de la télécommande de réglages du moniteur Hantarex (fréquence H/V, gain RVB, luminosité, contraste).

## 🕹️ Phase 4 : Câblage des Contrôles & Audio
- [ ] Brancher les joysticks et les 3-4 premiers boutons de chaque joueur sur le peigne JAMMA d'origine (via soudure ou cosses).
- [ ] Réaliser le câblage complémentaire (Kick Harness) pour les boutons 5 et 6 de chaque joueur, et le relier au connecteur prévu sur le Recalbox RGB JAMMA 2.
- [ ] Configurer et mapper les boutons dans le menu Recalbox.
- [ ] Installer et tester la sélection de roms (Double Dragon, Shinobi, Flash, Golden Axe, Fa18, Streetfighter) (voir [liste_jeux.md](liste_jeux.md)).
- [ ] Tester les boutons dans Street Fighter (vérifier les coups légers, moyens, forts et l'input lag).
- [ ] Vérifier la sortie audio : ajuster le potentiomètre d'amplification sur la carte Recalbox RGB JAMMA 2.

## 🛠️ Phase 5 : Intégration Finale & Finitions
- [ ] Fixer proprement le Raspberry Pi 5 et sa carte d'interface à l'intérieur du châssis en bois de la borne.
- [ ] Remplacer le néon d'origine du Marquee (bandeau lumineux du haut) par un bandeau LED 12V branché sur l'alimentation de la borne.
- [ ] Organiser et attacher les câbles internes avec des colliers de serrage.

