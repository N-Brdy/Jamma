# Ton parcours Jamma

**En bref :** tu vas rouvrir ta borne d'arcade et la faire revivre. D'abord tu
retrouves et rassembles le matériel, ensuite tu obtiens une **image 15 kHz sur
l'écran cathodique**, puis tu reconstruis le panel pour jouer. Chaque mission
est courte, se termine par quelque chose à montrer, et **débloque une
récompense**.

Avant la première séance, découvre [à quoi cela sert et ce que tu vas
apprendre](les-bases.md#pourquoi). Le **[guide des bases](les-bases.md)** est ton
aide-mémoire : chaque mission ci-dessous te renvoie aux notions utiles, à lire
quand tu en as besoin.

**Important :** avant d'ouvrir la borne, lis la **[fiche sécurité CRT](securite-crt.md)**.
Le tube garde une très haute tension ; on ne touche au châssis qu'avec le papa,
borne débranchée.

## Comment avancer par toi-même

- Tu pilotes les essais, les observations, le carnet et les choix ordinaires. Le
  papa intervient pour la haute tension, la soudure les premières fois, les
  achats et les vérifications à deux.
- Vise des séances de 30 à 60 minutes. Les durées ci-dessous sont indicatives ;
  tu peux couper une mission en deux.
- Une mission à la fois. Coche « terminé » quand sa preuve existe.
- **Démarre par 10 minutes seulement** : la première action de chaque mission est
  toujours petite et ne demande aucune décision. Ensuite, tu continues si tu veux.
- Si tu bloques pendant 15 minutes : note le message exact, prends une photo,
  puis écris une question précise dans le [journal](journal.md).
- **Ne finis jamais une séance sur un blocage.** Termine sur une petite victoire
  et note la prochaine petite action (10 minutes maximum) dans le [carnet](carnet.md).

**Notre chaîne :** matériel → Recalbox (Pi 5) → signal 15 kHz (HAT Recalbox RGB
JAMMA 2) → écran CRT Hantarex → joysticks et boutons → haut-parleurs.

---

## Bloc A — Ça démarre aujourd'hui

Ces trois missions ne demandent ni outil ni démontage : elles servent à se
lancer et à préparer tout le reste.

## Mission 1 — Rassembler le matériel

**Pour comprendre :** [électronique et logiciel](les-bases.md#electronique).

**15 min · aucun outil · résultat : tout le matériel au même endroit.**

1. Cherche le **Raspberry Pi 5** : il est rangé quelque part dans les cartons.
   Ouvre les cartons un par un, sans tout vider sur le sol.
2. Rassemble le kit **Recalbox RGB JAMMA 2** : la carte, son boîtier de
   protection et sa connectique.
3. Ajoute l'**alimentation USB-C officielle**, la **carte microSD**, les
   **joysticks et boutons Sanwa**, le **fer à souder** et le **multimètre**.
4. Pose tout dans **une seule boîte** que tu étiquettes « Projet Jamma ».
5. Prends une photo d'ensemble et coche l'inventaire dans
   [la fiche matériel](../hardware/materiel.md#inventaire).

**Terminé quand :** la photo est prise et chaque élément de l'inventaire a un statut.

**À la clé :** le projet a officiellement commencé — et la prochaine séance
démarre en une minute, sans rien chercher.

**Si ça bloque :** ne cherche pas tout aujourd'hui. Note ce qui manque dans le
[journal](journal.md) et continue avec ce que tu as.

## Mission 2 — État des lieux de la borne

**Pour comprendre :** [arcade et JAMMA](les-bases.md#arcade) et la
[fiche sécurité CRT](securite-crt.md).

**30–45 min · appareil photo ou téléphone · résultat : la borne est photographiée et comprise.**

**Avant de commencer : lis la [fiche sécurité CRT](securite-crt.md) en entier.**

1. Photographie l'extérieur : face, côté, marquee, panel, monnayeur.
2. Ouvre la porte et photographie l'intérieur : alimentation, transformateur
   d'isolement, peigne JAMMA bleu, haut-parleurs, câblage.
3. Photographie le moniteur : châssis **Hantarex Polo 25"**, platine de cou, la
   **télécommande OC 03** et sa résistance **R403 brûlée**.
4. Enregistre les photos dans `assets/photos/` avec des noms explicites
   (voir `assets/photos/README.md`).
5. Note dans le [carnet](carnet.md) **trois règles de sécurité** que tu sais
   expliquer avec tes mots.

**Terminé quand :** les photos sont enregistrées et tu peux expliquer ce qui est
dangereux (tube, secteur) et ce qui est sûr à toucher borne débranchée.

**À la clé :** tu connais ta borne par cœur — et tu as déjà repéré ce qu'il faut réparer.

**Si ça bloque :** prends moins de photos, mais garde au minimum le peigne JAMMA,
le châssis et la télécommande OC 03.

## Mission 3 — Recalbox démarre sur la TV

**Pour comprendre :** [électronique et logiciel](les-bases.md#electronique).

**45–60 min · TV avec prise HDMI · résultat : Recalbox tourne et tu joues.**

On valide d'abord le logiciel sur une TV **avant** de toucher à la borne.

1. Télécharge l'image **Recalbox pour Raspberry Pi 5** sur le site officiel ;
   note la version.
2. Écris l'image sur la **microSD** avec Raspberry Pi Imager ou balenaEtcher.
3. Insère la carte dans le Pi, branche l'alimentation USB-C officielle et un
   câble HDMI vers la TV. **Ne branche pas encore le HAT sur la borne.**
4. Démarre : l'écran d'accueil Recalbox doit s'afficher.
5. Note la version dans [la fiche de configuration](configuration.md), branche
   une manette USB si tu en as une et lance vite une partie.

**Terminé quand :** l'écran Recalbox s'affiche sur la TV et la version est notée.

**À la clé :** 🎮 une première partie sur la TV — tu as déjà une « console
d'arcade » qui fonctionne, avant même d'ouvrir la borne.

**Si ça bloque :** écran noir → change de câble HDMI puis de port, vérifie que la
carte est bien enfoncée. Note le dernier point qui fonctionne avant de demander.

---

## Bloc B — Au cœur de la machine

Ces missions touchent l'électronique et la haute tension : **avec le papa**.

## Mission 4 — Comprendre l'alimentation

**Pour comprendre :** [électronique et logiciel](les-bases.md#electronique) et la
[fiche sécurité CRT](securite-crt.md).

**30–45 min · multimètre · borne débranchée · résultat : le circuit d'alimentation est compris.**

1. Borne **débranchée**, repère l'alimentation arcade d'origine et le gros
   **transformateur d'isolement** à gauche.
2. Repère le peigne JAMMA et ses broches **+5 V** et **+12 V**.
3. Contrôle au multimètre, en mode continuité : fusibles, arrivée du
   transformateur, masses.
4. Vérifie visuellement : aucun condensateur gonflé, aucune trace noircie, aucun
   fil dénudé.
5. Note les mesures dans le [carnet](carnet.md#alimentation--mission-4) et prends une photo.

**Terminé quand :** les fusibles sont testés, les mesures sont notées et aucune
anomalie n'est visible.

**À la clé :** premier vrai usage du multimètre — l'alimentation n'est plus une
boîte noire.

**Si ça bloque :** si tu ne sais pas quel fusible tester, note la référence
exacte et demande au papa avant de continuer.

## Mission 5 — Réparer la télécommande OC 03

**Pour comprendre :** [soudure et composants](les-bases.md#soudure).

**1 à 2 séances de 45 min · fer à souder et multimètre · avec le papa · résultat : la télécommande fonctionne.**

1. Rassemble les pièces : **R403** (1 kΩ, ou 1,8 kΩ selon la révision), **D401**
   (BA159), **C401** (1 µF / 100 V).
2. Dessoude la résistance brûlée, déssoude et contrôle la diode.
3. Monte les composants neufs en respectant le sens de la diode, puis contrôle au
   multimètre : résistance proche de 1 kΩ, diode passante dans un seul sens.
4. **Avant toute remise sous tension**, vérifie le sens et l'alignement du
   connecteur **J407** à deux (un décalage de broches peut recréer le court-circuit).
5. Photographie les soudures avant/après et note les mesures dans le
   [carnet](carnet.md#télécommande-oc-03--mission-5).

**Terminé quand :** les mesures sont conformes, le connecteur J407 est vérifié à
deux et le remontage est prêt pour l'essai de la mission 8.

**À la clé :** tu as réparé une vraie carte d'époque — et l'écran deviendra
réglable au pixel près.

**Si ça bloque :** une soudure ratée se refait, ce n'est pas grave. Demande au
papa pour la première soudure si tu hésites. Ne force jamais un composant.

## Mission 6 — Décharger le tube et nettoyer le châssis

**Pour comprendre :** [haute tension](les-bases.md#haute-tension) et à nouveau la
[fiche sécurité CRT](securite-crt.md).

**45 min · avec le papa · pinceau, aspirateur brosse, outil de décharge · résultat : un châssis propre.**

**Avant de commencer : relis la [fiche sécurité CRT](securite-crt.md) en entier.**

1. Débranche la borne et laisse-la reposer.
2. Avec le papa, **décharge le tube** selon la procédure, puis vérifie au multimètre.
3. Dépoussière le châssis principal et la platine de cou : pinceau doux et
   aspirateur en position brosse. Jamais d'eau.
4. Contrôle visuel : soudures fendillées, condensateurs bombés, connecteurs desserrés.
5. Photos avant/après et note ce que tu as observé.

**Terminé quand :** le tube est déchargé et vérifié, le châssis est propre et les
anomalies éventuelles sont listées.

**À la clé :** la photo avant/après la plus satisfaisante du projet — et une
machine qui respire.

**Si ça bloque :** on ne se presse pas. Dès qu'un doute apparaît, on s'arrête et
on note la question.

---

## Bloc C — La borne revit

C'est le grand moment : le premier signal sur l'écran d'origine.

## Mission 7 — Monter le Pi et le Recalbox RGB JAMMA 2

**Pour comprendre :** [électronique](les-bases.md#electronique) et
[vidéo CRT](les-bases.md#video).

**45–60 min · résultat : tout est en place, plus qu'un bouton à appuyer.**

1. Enfiche le **Recalbox RGB JAMMA 2** sur le Raspberry Pi 5, puis installe
   l'ensemble dans son boîtier de protection.
2. Vérifie que la sortie est bien en **15 kHz analogique** (mode CRT) avant tout
   branchement sur la borne : relis la règle d'or dans
   [la configuration](configuration.md#signal-vidéo).
3. Relie la carte au **peigne JAMMA bleu** (borne débranchée) : rouge, vert,
   bleu, synchro, masse.
4. Fais la **checklist vidéo à deux** (avec le papa) : mode 15 kHz, connexions,
   masse, alimentation du Pi.
5. Prends des photos du montage et signe la checklist dans le
   [carnet](carnet.md#checklist-15-khz--mission-7).

**Terminé quand :** la checklist 15 kHz est signée à deux et tout est fixé sans
câble qui pend.

**À la clé :** tout est en place — il ne reste qu'à appuyer sur le bouton.

**Si ça bloque :** dans le doute, **on ne branche pas l'écran**. Note ce qui n'est
pas sûr et reprends la mission précédente.

## Mission 8 — Premier allumage de l'écran CRT 🏆

**Pour comprendre :** [vidéo CRT](les-bases.md#video).

**15–30 min · avec le papa · résultat : la borne s'allume.**

1. Vérifie une dernière fois la checklist de la mission 7.
2. Branche la borne, puis mets-la sous tension.
3. Observe : l'écran d'accueil Recalbox doit apparaître sur le Hantarex, stable,
   sans sifflement anormal.
4. Si l'image est instable, **coupe l'alimentation** et vérifie la synchro avant
   de recommencer.
5. Prends une photo ou une courte vidéo de l'écran Recalbox sur le CRT.

**Terminé quand :** Recalbox s'affiche sur le CRT et la borne ne montre aucun
signe anormal.

**À la clé :** 🏆 **LE moment** — la borne revit. Montre-la tout de suite à la
famille : c'est l'image dont tu te souviendras.

**Si ça bloque :** aucune image → reviens à la mission 7. Image qui roule →
problème de synchro : on note et on ajuste avec le papa.

## Mission 9 — Régler l'image

**Pour comprendre :** [vidéo CRT](les-bases.md#video).

**30–45 min · télécommande OC 03 réparée · résultat : une image de qualité arcade.**

1. Avec la télécommande OC 03, règle la taille, la position et la synchro
   horizontale/verticale.
2. Règle la luminosité, le contraste et les gains RVB.
3. Lance un jeu d'époque et active le mode **pixel-perfect**.
4. Prends une photo « avant / après » réglages.
5. Note les réglages retenus dans le [carnet](carnet.md#réglages-image--missions-8-et-9).

**Terminé quand :** un jeu s'affiche plein écran, droit et sans distorsion, avec
des couleurs correctes.

**À la clé :** la différence avant/après est spectaculaire — l'image est celle
d'une vraie borne.

**Si ça bloque :** change **un seul réglage à la fois** et note son effet, sinon
tu ne sauras plus lequel agit.

---

## Bloc D — Jouer, puis reconstruire le panel

La borne fonctionne : on joue, puis on lui offre un vrai panel de jeu de combat.

## Mission 10 — Tester les contrôles d'origine

**Pour comprendre :** [arcade et JAMMA](les-bases.md#arcade).

**30 min · résultat : première partie sur la borne.**

1. Vérifie le raccordement des contrôles sur le peigne JAMMA : joystick 1P/2P,
   boutons 1 à 3, Start, Crédit.
2. Dans Recalbox, lance la configuration des contrôles et mappe chaque entrée.
3. Lance **Double Dragon** (2 boutons, parfait pour commencer).
4. Teste le joystick et les boutons, note un éventuel temps de réponse.

**Terminé quand :** tu joues une vraie partie au joystick et aux boutons
d'origine, et le mapping est noté.

**À la clé :** 🕹️ première vraie partie **sur la borne** — l'objectif du projet
est atteint en vrai.

**Si ça bloque :** un bouton ne répond pas → teste-le au multimètre et vérifie sa
broche sur le peigne avant de tout refaire.

## Mission 11 — Concevoir le panel Street Fighter II

**Pour comprendre :** [CAO et fabrication](les-bases.md#fabrication).

**2 à 3 séances de 45 min · Fusion 360 · résultat : un panel dessiné et un prototype en main.**

1. Mesure la plaque actuelle et les points de fixation sur la caisse ; note-les
   dans les [notes de montage](../hardware/notes-montage.md).
2. Sur Fusion 360, dessine l'esquisse 2D : **Ø30 mm** pour les 12 boutons de jeu
   et **Ø24 mm** pour les 4 boutons Start/Select.
3. Choisis le layout (**Vewlix** ou **Sega Astro City**) et place les boutons.
4. Modélise les supports de fixation sur la caisse et les bagues des joysticks
   **Sanwa JLF**.
5. Exporte l'esquisse en **DXF** pour la découpe.
6. Découpe un prototype en carton ou MDF 3 mm au laser, monte à blanc et teste
   l'ergonomie.

**Terminé quand :** le DXF est exporté et le prototype est testé en main,
ergonomie validée.

**À la clé :** tu tiens ton panel dans les mains et tu l'essaies « à blanc » avant
la découpe finale.

**Si ça bloque :** commence par une petite pièce test (une bague de joystick)
pour vérifier les cotes avant de tout dessiner.

## Mission 12 — Fabriquer le panel final

**Pour comprendre :** [CAO et fabrication](les-bases.md#fabrication).

**2 à 3 séances + impressions · Prusa Core One · résultat : un panel de vraie borne.**

1. Découpe la plaque finale (PMMA/Plexiglas double épaisseur ou MDF peint) selon
   le DXF validé.
2. Imprime en 3D sur la Prusa Core One : charnières et équerres, supports Sanwa
   JLF, support du Pi 5 et de son boîtier.
3. Monte les joysticks **Sanwa JLF-TP-8YT** et les boutons **OBSF-30 / OBSF-24**.
4. Fixe le panel sur la caisse en bois : démontable et solide.
5. Teste à deux joueurs et note les ajustements.

**Terminé quand :** le panel est monté, solide, et une partie à deux joueurs est
confortable.

**À la clé :** la sensation d'une vraie borne d'arcade sous les doigts.

**Si ça bloque :** corrige d'abord la petite pièce test plutôt que de réimprimer
tout le support.

## Mission 13 — Kick harness et 6 boutons

**Pour comprendre :** [arcade et JAMMA](les-bases.md#arcade) et
[soudure](les-bases.md#soudure).

**45–60 min · câble kick harness · résultat : Street Fighter II complet.**

1. Le standard JAMMA ne gère que 3 à 4 boutons : prépare le **kick harness** pour
   les boutons 4, 5 et 6 de chaque joueur.
2. Relie-le au connecteur prévu sur le Recalbox RGB JAMMA 2.
3. Mappe les 6 boutons de chaque joueur dans Recalbox.
4. Dans **Street Fighter II**, teste les coups légers, moyens et forts (poings et
   pieds).
5. Note le mapping complet dans le [carnet](carnet.md#mapping-des-contrôles--missions-10-et-13).

**Terminé quand :** les 6 boutons des deux joueurs répondent correctement dans
Street Fighter II.

**À la clé :** ⚔️ Street Fighter II jouable à 100 % — le jeu pour lequel le panel
a été refait.

**Si ça bloque :** teste un bouton à la fois et repère la broche fautive avant de
refaire tout le câblage.

## Mission 14 — Le son

**Pour comprendre :** [électronique](les-bases.md#electronique).

**30 min · résultat : le son sort des haut-parleurs de la borne.**

1. Vérifie le raccordement audio entre la carte Recalbox RGB JAMMA 2 et les
   haut-parleurs d'origine.
2. Ajuste le **potentiomètre d'amplification** de la carte.
3. Teste avec un jeu : son audible, sans grésillement.
4. Note le réglage dans le [carnet](carnet.md#son--mission-14).

**Terminé quand :** le son sort des haut-parleurs de la borne et se règle proprement.

**À la clé :** l'ambiance sonore arcade complète — la borne « sonne » comme dans
le souvenir.

**Si ça bloque :** si le son grésille, baisse le potentiomètre et vérifie les
masses avant de changer quoi que ce soit.

---

## Bloc E — Finir et célébrer

## Mission 15 — Intégration finale et finitions

**Pour comprendre :** [électronique](les-bases.md#electronique) et
[fiabilité](les-bases.md#fiabilite).

**2 séances · résultat : une borne présentable de partout.**

1. Fixe proprement le Pi 5, sa carte d'interface et l'alimentation à l'intérieur
   de la caisse.
2. Organise les câbles avec des colliers, sans pincement ni traction.
3. Remplace le néon d'origine du marquee par un **bandeau LED 12 V** branché sur
   l'alimentation de la borne.
4. Prépare un **allumage et une extinction propres** (bouton ou menu Recalbox) :
   jamais de coupure sauvage, qui peut corrompre la carte SD.
5. Fais le tour : photos intérieur et extérieur.

**Terminé quand :** aucun câble ne pend, le marquee s'allume, l'extinction est
propre et les photos le montrent.

**À la clé :** la borne est présentable de partout — prête à être montrée.

**Si ça bloque :** garde chaque modification réversible et note les branchements
avant de les refaire.

## Mission 16 — Inauguration 🎉

**Rien de technique : c'est le moment de jouer.**

**Une soirée · résultat : la borne est utilisée par tout le monde.**

1. Fais une petite démo de la restauration : photos **avant / après**.
2. Explique en deux minutes la chaîne : matériel → Recalbox → 15 kHz → CRT.
3. Lance un tournoi **Street Fighter II** ou une session coop **Double Dragon /
   Golden Axe** avec la famille et un ami.
4. Prends une photo de la soirée et ajoute-la au [mur des victoires](carnet.md#mur-des-victoires).

**Terminé quand :** la borne a servi toute une soirée et la photo est dans le carnet.

**À la clé :** 🎉 la récompense finale : ta borne d'arcade est vivante, et c'est
toi qui l'as fait revivre.

**Si ça bloque :** rien ne bloque une soirée. Si un jeu pose problème, note-le et
garde la correction pour un bonus.

---

## Après cette première réussite

La borne fonctionne : voici des idées de **bonus**, à choisir librement, qui ne
font pas partie du parcours.

- Restaurer l'esthétique : retoucher une rayure, nettoyer le T-molding, soigner le
  monnayeur.
- Ajouter des jeux ou des systèmes, et affiner les réglages pixel-perfect.
- Installer un vrai bouton d'allumage (shutdown propre) et un ventilateur discret.
- Ajouter des notes de maintenance et une sauvegarde de la configuration dans
  [la fiche de configuration](configuration.md).
