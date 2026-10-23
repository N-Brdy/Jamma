# Les bases pour comprendre Jamma

**En bref :** tu remets en marche une borne d'arcade d'époque. Un petit
ordinateur (Raspberry Pi 5) fait tourner l'émulation, une carte spéciale
transforme son signal numérique en un signal **analogique 15 kHz** que le vieil
écran cathodique comprend, et les joysticks parlent à la borne par le **peigne
JAMMA**. Tu vas apprendre l'électronique, la soudure, la vidéo, la conception
3D et la méthode : tester, mesurer, expliquer.

Ce guide est ta boîte à outils : lis « Pourquoi », puis les sections indiquées
dans ta mission. Tu n'as pas besoin de tout mémoriser avant de commencer.

## Où chercher ?

| Ta question | Explication | Quand ? |
| --- | --- | --- |
| Pourquoi rénover cette borne ? | [Pourquoi](#pourquoi) | Avant de commencer |
| C'est quoi une borne, un peigne JAMMA, un panel ? | [Arcade et JAMMA](#arcade) | Missions 2 et 10 |
| Pi, HAT, Recalbox, microSD : c'est quoi ? | [Électronique et logiciel](#electronique) | Missions 3, 4 et 7 |
| Pourquoi le signal 15 kHz est-il si important ? | [Vidéo CRT](#video) | Missions 7 à 9 |
| Le tube électrocute-t-il ? | [Haute tension](#haute-tension), [fiche sécurité](securite-crt.md) | Missions 2 et 6 |
| Comment souder et reconnaître une résistance ? | [Soudure et composants](#soudure) | Mission 5 |
| Du dessin à la pièce découpée ou imprimée ? | [CAO et fabrication](#fabrication) | Missions 11 et 12 |
| Comment savoir si ça marche vraiment ? | [Fiabilité et essais](#fiabilite) | Toutes les missions |
| Je suis bloqué : par où commencer ? | [Dépannage](#depannage) | Dès que nécessaire |

<a id="pourquoi"></a>

## Pourquoi rénover cette borne ?

Cette borne a une histoire : c'est une machine d'époque, avec un écran
cathodique qui ne se fabrique plus. La rénover, c'est lui redonner une seconde
vie plutôt que de la laisser s'abîmer, et profiter du plaisir très particulier
d'un jeu d'arcade sur son écran d'origine.

C'est un projet **pour soi** : il n'y a pas de prime à la clé, la récompense est
dans le projet lui-même. Chaque mission débloque quelque chose de visible :
d'abord le matériel rassemblé, puis une image sur le CRT, puis une vraie partie.
La borne « grandit » sous tes yeux.

### Ce que tu apprends, toi

| En faisant… | Tu apprends à… |
| --- | --- |
| L'inventaire et les essais | Organiser un chantier et avancer par étapes |
| La réparation de la télécommande | Lire un schéma, reconnaître un composant, souder proprement |
| Les mesures au multimètre | Vérifier une alimentation et prouver un résultat |
| L'allumage du CRT en 15 kHz | Comprendre la vidéo analogique et la synchronisation |
| Le panel sur Fusion 360 | Concevoir, exporter et fabriquer une pièce |
| La démo et le journal | Expliquer et transmettre ton travail |

**Petit défi :** repère sur la borne la pièce qui te plaît le moins (fine
rayure, bouton fatigué, marquee éteint…). Note-la dans le [journal](journal.md) :
ce sera un bonus de finition après l'inauguration.

<a id="arcade"></a>

## Arcade et JAMMA

Une **borne d'arcade** est un meuble contenant un écran, un système de jeu, un
panel de commandes, des haut-parleurs et une caisse pour l'argent.

- Le **peigne JAMMA** est un grand connecteur en bas de la borne. C'est le
  standard qui relie la carte du jeu au reste : vidéo (rouge, vert, bleu,
  synchro, masse), alimentation (+5 V, +12 V), contrôles (joystick et boutons),
  son et crédits.
- Le **panel** est la planche des commandes. Le standard JAMMA ne gère
  nativement que 3 à 4 boutons par joueur ; **Street Fighter II** en demande 6.
  Les boutons 4 à 6 passent donc par un câblage additionnel appelé **kick
  harness**.
- Le **marquee** est le bandeau éclairé en haut de la borne.

**Astuce :** tout ce qui se branche sur le peigne JAMMA se fait **borne
débranchée**. On vérifie toujours deux fois avant de remettre sous tension.

<a id="electronique"></a>

## Électronique et logiciel : le petit ordinateur du montage

- Le **Raspberry Pi 5** est un petit ordinateur : il fait tourner le logiciel
  d'émulation.
- **Recalbox** est le système (l'« OS ») installé sur une **carte microSD**. On
  écrit l'image de Recalbox sur la carte depuis un PC, puis on la met dans le Pi.
- Le **Recalbox RGB JAMMA 2** est un « HAT » : une carte qui s'enfiche sur le Pi
  et fournit la sortie vidéo analogique 15 kHz, l'amplification audio et le
  raccordement du peigne JAMMA.
- L'**alimentation officielle USB-C (5 V / 5 A)** alimente le Pi de façon fiable.
- Le **multimètre** vérifie une tension ou une continuité. C'est l'outil qui
  transforme une impression en mesure.

**Le Pi seul ne suffit pas :** sans le HAT, il ne sait pas parler à l'écran
d'époque ni aux contrôles de la borne.

<a id="video"></a>

## Vidéo CRT : pourquoi 15 kHz ?

L'écran **Hantarex Polo 25"** est un écran **cathodique (CRT)** prévu pour le
standard arcade : un signal **analogique RVB à 15,625 kHz** (on dit « 15 kHz »).
Un PC moderne ou un Pi en HDMI sortent un signal **numérique à 31 kHz ou plus**.

> [!WARNING]
> Envoyer un signal 31 kHz ou numérique à un écran 15 kHz peut l'endommager
> (sifflement aigu, image illisible). C'est pour cela qu'on utilise le HAT
> Recalbox RGB JAMMA 2, qui produit automatiquement le bon signal.

Le mode **pixel-perfect** fait afficher chaque jeu dans sa résolution d'origine
(240p, 320×224 pour la Neo-Geo, etc.) : l'image est nette et fidèle, comme à
l'époque.

<a id="haute-tension"></a>

## Haute tension : le tube

Le tube cathodique fonctionne avec plusieurs milliers de volts, **conservés même
après extinction**. On ne le décharge jamais seul et jamais à main nue. La
procédure complète est dans la **[fiche sécurité CRT](securite-crt.md)** : à
relire avant toute intervention sur le châssis.

<a id="soudure"></a>

## Soudure et composants

La **télécommande OC 03** du moniteur a une résistance brûlée : c'est l'occasion
d'apprendre à souder.

- La **résistance** limite le courant. Elle a une valeur en ohms (Ω) et un sens
  indifférent.
- La **diode** ne laisse passer le courant que dans un seul sens : elle a un sens
  à respecter.
- Le **condensateur** stocke une petite charge. Il a aussi un sens (patte + et −).

Bonnes pratiques : fer chaud mais pas trop, une soudure brillante et lisse, pas
de pont entre deux pistes, on déssoude proprement avant de remettre un composant.

<a id="fabrication"></a>

## CAO et fabrication : du dessin à la pièce

- **Fusion 360** sert à dessiner le panel en 3D : l'esquisse 2D (les trous des
  boutons), puis les supports de fixation.
- L'export **DXF** est le fichier de découpe envoyé à la **découpeuse laser**.
- L'impression 3D sur la **Prusa Core One** fabrique les supports, les bagues de
  joystick et le boîtier du Pi.
- On imprime toujours **une petite pièce test** avant la pièce finale, pour
  vérifier les cotes sans gaspiller de matière.

<a id="fiabilite"></a>

## Fiabilité : de « ça marche une fois » à une preuve

Un montage est fiable quand on peut le montrer **plusieurs fois**, dans les
mêmes conditions. Les règles :

- **Une seule variable à la fois** : on change un réglage, on observe, on note.
- **On photographie avant / après** : la photo est la preuve.
- **On note même les échecs** : un essai raté apprend autant qu'une réussite.

<a id="depannage"></a>

## Dépanner sans tout changer

1. Repère le **dernier point qui fonctionnait**.
2. Note le **message ou le symptôme exact** (photo, capture).
3. **Sépare les problèmes** : est-ce l'alimentation, le câble, le réglage ou le
   logiciel ?
4. Change **un seul élément**, puis reteste.
5. Si tu bloques plus de 15 minutes : écris une question précise dans le
   [journal](journal.md) et demande au papa.

## Pour passer à l'action

Ouvre le **[parcours](parcours.md)** et commence par la
**[mission 1](parcours.md#mission-1--rassembler-le-matériel)** : retrouver le
matériel. Tout le reste s'enchaîne à partir de là.
