# Carnet de travail

À remplir au fil des [missions](parcours.md), sans tout préparer d'avance.
Une case cochée signifie que le résultat a été montré et sa preuve enregistrée.

**Un mot inconnu ?** Consulte le [guide des bases et son sommaire par question](les-bases.md).
Avant d'ouvrir la borne : [fiche sécurité CRT](securite-crt.md).

## Tableau de progression

| Terminé | Mission | Résultat à montrer | Récompense | Preuve / date |
| --- | --- | --- | --- | --- |
| [ ] | 1 — Rassembler | Matériel réuni et inventaire complété | Le projet a commencé | |
| [ ] | 2 — État des lieux | Photos de la borne et 3 règles de sécurité expliquées | Tu connais ta borne | |
| [ ] | 3 — Recalbox sur la TV | Recalbox s'affiche sur la TV, version notée | 🎮 Première partie sur la TV | |
| [ ] | 4 — Alimentation | Fusibles testés et mesures notées | Premier usage du multimètre | |
| [ ] | 5 — Télécommande OC 03 | R403/D401/C401 contrôlés, J407 vérifié | Tu as réparé une carte d'époque | |
| [ ] | 6 — Décharge et nettoyage | Tube déchargé, châssis propre, photos avant/après | La plus belle photo avant/après | |
| [ ] | 7 — Montage Pi + HAT | Checklist 15 kHz signée à deux | Tout est en place | |
| [ ] | 8 — Premier allumage CRT | Recalbox s'affiche sur le CRT | 🏆 La borne revit | |
| [ ] | 9 — Régler l'image | Photo avant/après réglages | Une image de qualité arcade | |
| [ ] | 10 — Contrôles d'origine | Partie jouée, mapping noté | 🕹️ Première partie sur la borne | |
| [ ] | 11 — Panel Fusion 360 | DXF exporté, prototype testé en main | Tu tiens ton panel | |
| [ ] | 12 — Panel final | Panel monté, partie à deux confortable | La sensation d'une vraie borne | |
| [ ] | 13 — Kick harness | 6 boutons des 2 joueurs testés dans SF2 | ⚔️ Street Fighter II complet | |
| [ ] | 14 — Son | Son audible et réglage noté | L'ambiance sonore arcade | |
| [ ] | 15 — Intégration finale | Photos, marquee allumé, extinction propre | La borne est présentable | |
| [ ] | 16 — Inauguration | Photo de la soirée | 🎉 La soirée arcade | |

**Mission en cours :** 1 — Rassembler le matériel.
**Prochaine petite action (≤ 10 min) :** chercher le Raspberry Pi 5 dans les cartons.
**Besoin du papa, si nécessaire :** rien pour l'instant.

## Inventaire — mission 1

Compléter l'[inventaire dans la fiche matériel](../hardware/materiel.md#inventaire),
puis noter ici la date et la photo d'ensemble.

- Date de l'inventaire : …
- Photo d'ensemble : …
- Éléments manquants ou à acheter : …

## Règles de sécurité — mission 2

Noter **trois** règles que tu sais expliquer avec tes mots (sans recopier la
fiche). Détail complet : [fiche sécurité CRT](securite-crt.md).

1. …
2. …
3. …

## Alimentation — mission 4

Écrire « attendu » et « mesuré » pour chaque point de contrôle.

| Point mesuré | Valeur attendue | Valeur mesurée | OK ? |
| --- | --- | --- | --- |
| Fusible principal | Continuité | | |
| Arrivée transformateur d'isolement | Tension présente / continuité | | |
| Broche +5 V du peigne JAMMA | ~5 V | | |
| Broche +12 V du peigne JAMMA | ~12 V | | |

Anomalies visuelles observées : …

## Télécommande OC 03 — mission 5

| Composant | Valeur / contrôle | Mesure obtenue | OK ? |
| --- | --- | --- | --- |
| R403 (résistance) | ~1 kΩ (ou 1,8 kΩ) | | |
| D401 (diode BA159) | Passante dans un seul sens | | |
| C401 (condensateur) | 1 µF / 100 V, remplacé | | |
| Connecteur J407 | Sens et alignement vérifiés à deux | | |

Photo des soudures avant/après : …

## Checklist 15 kHz — mission 7

À cocher **à deux** (avec le papa) avant tout branchement sur le CRT.
Règle d'or dans [la configuration](configuration.md#signal-vidéo).

- [ ] Recalbox détecte le HAT Recalbox RGB JAMMA 2.
- [ ] La sortie est bien en 15 kHz analogique (mode CRT).
- [ ] Le peigne JAMMA est relié : rouge, vert, bleu, synchro, masse.
- [ ] La masse est commune et correcte.
- [ ] L'alimentation du Pi est fiable (USB-C officielle ou +5 V de la borne).
- [ ] Aucun câble ne pend ni ne tire sur un connecteur.
- [ ] Bornes débranchées au moment du branchement.

Signé à deux le : …

## Réglages image — missions 8 et 9

Un seul réglage modifié à la fois, puis observation.

| Essai | Réglage changé | Observation | Photo |
| --- | --- | --- | --- |
| | | | |
| | | | |
| | | | |

## Mapping des contrôles — missions 10 et 13

| Joueur | Bouton physique | Fonction Recalbox | Test OK ? |
| --- | --- | --- | --- |
| 1P | Joystick | Haut / bas / gauche / droite | |
| 1P | Bouton 1 à 6 | | |
| 2P | Joystick | Haut / bas / gauche / droite | |
| 2P | Bouton 1 à 6 | | |

## Son — mission 14

- Position du potentiomètre d'amplification : …
- Test audio (jeu utilisé) : …
- Grésillements ou problème observé : …

## Mur des victoires

Les photos **avant / après** qui montrent l'avancée du projet. Ajouter une ligne
à chaque mission marquante.

| Mission | Avant | Après |
| --- | --- | --- |
| 6 — Châssis | | |
| 8 — Premier allumage CRT | | |
| 9 — Image réglée | | |
| 12 — Panel final | | |
| 16 — Inauguration | | |

## Checklist inauguration — mission 16

- [ ] Image CRT stable et bien réglée.
- [ ] Joysticks et 6 boutons des deux joueurs fonctionnels.
- [ ] Son audible.
- [ ] Au moins trois jeux lancés sans problème.
- [ ] Démo « avant / après » prête.
- [ ] Photo de la soirée ajoutée au mur des victoires.

## Bilan, questions et décisions

Utiliser le [bilan de séance du journal](journal.md#bilan-de-séance-à-copier-modèle) et
ajouter un lien vers les preuves de ce carnet, sans recopier les mesures.
