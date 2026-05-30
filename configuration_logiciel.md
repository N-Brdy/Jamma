# 💾 Configuration Logiciel & Recalbox 15kHz

Ce document détaille la configuration logicielle recommandée pour ta borne avec le couple Raspberry Pi 5 et Recalbox RGB JAMMA 2.

---

## 💿 Choix du Système d'Exploitation (OS)

### 🥇 Recalbox (Recommandé)
Le choix de **Recalbox (version 10.0 ou ultérieure)** est optimal pour ce projet car :
*   Il supporte nativement le **Raspberry Pi 5**.
*   Il intègre la gestion complète et "Plug-and-Play" du HAT **Recalbox RGB JAMMA 2**.
*   Il gère automatiquement le signal **15kHz "Pixel-Perfect"** sans lignes de commande complexes (l'interface d'affichage s'adapte à la résolution native de chaque jeu d'époque : 240p, 480i, etc.).
*   Il gère le mapping des contrôles JAMMA et du Kick Harness directement depuis l'interface utilisateur.

---

## 🛠️ Configuration du Signal Vidéo

L'écran Hantarex **ne tolère pas** le signal 31kHz habituel des écrans PC VGA ou le signal numérique HDMI 1080p/4K. Envoyer un mauvais signal à l'écran peut l'endommager ou provoquer un sifflement aigu très désagréable avec une image illisible.

### Règle d'or
> [!WARNING]
> Ne branche jamais le Pi allumé sur le moniteur CRT tant que tu n'es pas sûr à 100 % que le Pi est configuré pour sortir un signal analogique **15.625 kHz / 50-60 Hz**. Il est recommandé de faire l'installation de Recalbox sur la carte SD sur ton PC, puis de brancher la carte sur le Pi déjà assemblé avec son HAT JAMMA et relié à la borne. Le système Recalbox détectera automatiquement le HAT RGB JAMMA au démarrage et adaptera le signal.

### Activation sur Recalbox
Si le système ne bascule pas automatiquement en mode CRT, tu peux forcer la configuration dans le fichier `recalbox.conf` accessible à la racine de la carte SD ou via réseau local :

```ini
# Activer le mode CRT pour le HAT Recalbox RGB JAMMA
crt.es_resolution=240p
crt.videomode=240p
```

---

## 🖥️ Commandes Utiles & Accès SSH

Pour administrer le Raspberry Pi à distance depuis ton PC Windows sur le même réseau local :

### Connexion SSH (PowerShell)
```powershell
# Connexion SSH sur Recalbox (mot de passe par défaut : recalboxroot)
ssh root@recalbox.local
```

### Vérifier l'état de la sortie vidéo
Pour s'assurer que le driver d'affichage (KMS) charge bien le mode DPI (GPIO analogique) sur le Raspberry Pi 5 :
```bash
# Vérifier si l'overlay d'affichage est chargé
dmesg | grep -i dpi
# ou pour lister les connecteurs vidéo reconnus
cat /sys/class/drm/*/status
```

### Redémarrer ou éteindre proprement via SSH
> [!TIP]
> Ne jamais éteindre la borne en coupant l'alimentation générale à la sauvage si le Pi est en train d'écrire sur la carte SD, cela pourrait corrompre le système. Utilise un script d'extinction propre (shutdown button) ou éteins depuis le menu de Recalbox ou en SSH :
```bash
shutdown -h now
```

