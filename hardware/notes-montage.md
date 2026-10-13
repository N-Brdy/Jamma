# Notes de montage

Mesures, cotes et emplacements utiles au montage. À compléter au fil des
missions, avec les [photos de référence](../assets/photos/README.md).

## Photos de référence

Photos prises en [mission 2](../docs/parcours.md#mission-2--état-des-lieux-de-la-borne) :

- Extérieur : face, côté, marquee, panel, monnayeur.
- Intérieur : alimentation, transformateur d'isolement, peigne JAMMA, haut-parleurs.
- Moniteur : châssis Hantarex Polo 25", platine de cou, télécommande OC 03
  (résistance R403 brûlée).

## Emplacements

| Élément | Emplacement retenu | Remarque |
| --- | --- | --- |
| Raspberry Pi 5 + HAT | | Fixation prévue en mission 15 |
| Alimentation du Pi | | USB-C officielle ou +5 V de la borne |
| MicroSD | Dans le Pi | Accès pour mise à jour |
| Bandeau LED du marquee | Haut de la borne | Alimentation 12 V |

## Cotes du panel — mission 11

À mesurer avant de dessiner sur Fusion 360.

| Cote | Valeur | Remarque |
| --- | --- | --- |
| Largeur de la plaque supérieure | | |
| Profondeur | | |
| Épaisseur | | |
| Entraxes des points de fixation | | |
| Débattement des joysticks | | |

Layout retenu : Vewlix / Sega Astro City / autre — à décider en mission 11.

## Impression 3D — mission 12

| Pièce | Matériau | Réglages notables | Statut |
| --- | --- | --- | --- |
| Bague / support joystick Sanwa JLF | | | |
| Boîtier de protection du Pi 5 | | | |
| Charnières / équerres du panel | | | |

Sauvegarde des fichiers : sources modifiables dans `hardware/cad/` et exports
d'impression dans `hardware/stl/` (à créer au premier enregistrement).

## Passage des câbles — mission 15

- [ ] Câbles regroupés avec des colliers, sans pincement ni traction.
- [ ] Aucun câble en contact avec une partie chaude ou sous tension.
- [ ] Accès conservé pour retirer le Pi sans tout débrancher.
- [ ] Extinction propre prévue (bouton ou menu Recalbox).
