# Configuration logiciel et remise en route

Ce document décrit la configuration retenue pour la borne : Raspberry Pi 5 +
**Recalbox** + carte **Recalbox RGB JAMMA 2**. Il se complète au fil des missions
et sert à refaire ou dépanner le montage.

## Système retenu : Recalbox

Le choix de **Recalbox** est pertinent pour ce projet car :

- il supporte nativement le **Raspberry Pi 5** ;
- il gère le HAT **Recalbox RGB JAMMA 2** de façon « plug-and-play » ;
- il gère automatiquement le signal **15 kHz pixel-perfect** (l'interface et les
  jeux s'adaptent à leur résolution d'origine : 240p, 480i, etc.) ;
- il gère le mapping des contrôles JAMMA et du kick harness depuis l'interface.

**Version installée :** à noter en [mission 3](parcours.md#mission-3--recalbox-démarre-sur-la-tv).

### Écrire la carte microSD

1. Télécharger l'image **Recalbox pour Raspberry Pi 5** sur le site officiel.
2. Flasher l'image sur la microSD avec **Raspberry Pi Imager** ou **balenaEtcher**.
3. Insérer la carte dans le Pi, démarrer d'abord **sur la TV en HDMI** (mission 3),
   avant tout branchement sur la borne.

<a id="signal-vidéo"></a>

## Configuration du signal vidéo

L'écran Hantarex **ne tolère pas** le signal 31 kHz habituel des écrans PC/VGA ni
le signal numérique HDMI 1080p/4K. Envoyer un mauvais signal peut l'endommager
ou provoquer un sifflement aigu avec une image illisible.

> [!WARNING]
> Ne branche jamais le Pi allumé sur le moniteur CRT tant que tu n'es pas sûr à
> 100 % qu'il est configuré pour sortir un signal analogique
> **15,625 kHz / 50–60 Hz**. Installe Recalbox sur la carte SD depuis le PC,
> branche d'abord le HAT sur le Pi, puis relie la borne : Recalbox détecte
> automatiquement le HAT RGB JAMMA au démarrage et adapte le signal.

Si le système ne bascule pas automatiquement en mode CRT, on peut le forcer dans
le fichier `recalbox.conf` (racine de la carte SD ou accès réseau) :

```ini
# Activer le mode CRT pour le HAT Recalbox RGB JAMMA
crt.es_resolution=240p
crt.videomode=240p
```

Réglages effectivement retenus sur la borne : à compléter en
[mission 9](parcours.md#mission-9--régler-limage).

## Accès SSH et commandes utiles

Pour administrer le Pi à distance depuis un PC sur le même réseau :

```bash
# Connexion SSH sur Recalbox (mot de passe par défaut : recalboxroot)
ssh root@recalbox.local
```

Vérifier l'état de la sortie vidéo (driver d'affichage, mode DPI / GPIO analogique) :

```bash
# Vérifier si l'overlay d'affichage est chargé
dmesg | grep -i dpi
# Lister les connecteurs vidéo reconnus
cat /sys/class/drm/*/status
```

## Éteindre proprement

> [!TIP]
> Ne jamais couper l'alimentation à la sauvage pendant que le Pi écrit sur la
> carte SD : cela peut corrompre le système. Utilise le menu de Recalbox, un
> bouton d'extinction propre (mission 15) ou l'arrêt en SSH :

```bash
shutdown -h now
```

## Sauvegarde et remise en route

Procédure à utiliser une fois la borne terminée (mission 15), pour pouvoir
refaire ou dépanner le montage.

- [ ] Version de Recalbox notée ci-dessus.
- [ ] Réglages du mode CRT (`recalbox.conf`) notés ci-dessus.
- [ ] Mapping des contrôles exporté et rangé (voir [carnet](carnet.md#mapping-des-contrôles--missions-10-et-13)).
- [ ] Liste des jeux installés à jour (voir [liste des jeux](liste-jeux.md)).
- [ ] Sauvegarde de la configuration réseau et des réglages dans un fichier local,
      hors du dépôt s'il contient des mots de passe.

**Remise en route :** carte microSD dans le Pi, Pi + HAT en place dans la caisse,
peigne JAMMA branché (borne débranchée), puis mise sous tension. En cas de doute
sur le signal, relire la [règle d'or](#signal-vidéo) avant de brancher le CRT.
