# Captures d'écran

Les captures d'écran servent à illustrer le projet sans exposer d'informations sensibles.

## Règles avant publication

- Masquer les adresses IP publiques.
- Masquer les adresses MAC si elles ne sont pas nécessaires.
- Masquer les clés, tokens, secrets et identifiants.
- Vérifier les noms d'utilisateur visibles.
- Vérifier les chemins contenant des informations personnelles.
- Éviter les captures contenant des exports complets pfSense, WireGuard ou SSH.

## Captures recommandées

- Vue globale de l'architecture HomeLab.
- Interface pfSense avec informations sensibles masquées.
- VLAN `HACKETH` dans la segmentation réseau.
- Exemple de scan Nmap réalisé en laboratoire contrôlé.
- Exemple de détection CrowdSec ou logs pfSense anonymisés.
- Capture du poste Kali HackEth après configuration.

## Captures déjà disponibles

Les captures détaillées de restauration, iVentoy et validation post-restauration sont publiées dans le dépôt `HackEth-Golden-Image`.

Inventaire détaillé :

```text
https://github.com/Mounir78190/HackEth-Golden-Image/blob/main/docs/screenshots.md
```

Captures principales disponibles :

- iVentoy avec ISO Clonezilla.
- Sélection du mode Clonezilla.
- Progression Partclone.
- Premier démarrage après restauration.
- Vérifications post-restauration.

## Organisation proposée

```text
screenshots/
|-- architecture/
|-- pfsense/
|-- kali/
|-- crowdsec/
`-- restore/
```

## Convention de nommage

Utiliser des noms simples et explicites :

```text
pfsense-vlan-hacketh.png
kali-tools-overview.png
crowdsec-alert-lab.png
clonezilla-restore-summary.png
```
