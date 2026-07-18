# Structure des dépôts

La structure validée sépare clairement l'infrastructure, le poste de travail, l'automatisation et la sauvegarde.

## Organisation logique

```text
HomeLab
|
`-- HackEth
    |-- HackEth-Bootstrap
    |-- HackEth-Golden-Image
    `-- iVentoy / boot réseau PXE
```

Sur GitHub, chaque bloc peut rester dans un dépôt séparé. Cela évite d'avoir un dépôt trop lourd et permet de présenter chaque compétence clairement.

## Dépôts

| Dépôt | Rôle | Description |
| --- | --- | --- |
| [HomeLab](https://github.com/Mounir78190/HomeLab) | Infrastructure parent | pfSense, VLAN, WireGuard, CrowdSec, approche SOC/Blue Team |
| [HackEth](https://github.com/Mounir78190/HackEth) | Sous-projet vitrine | Point d'entrée du poste Kali dans l'écosystème HomeLab |
| [HackEth-Bootstrap](https://github.com/Mounir78190/HackEth-Bootstrap) | Automatisation | Scripts permettant de reconstruire le poste Kali |
| [HackEth-Golden-Image](https://github.com/Mounir78190/HackEth-Golden-Image) | Sauvegarde et reprise | Golden Image Clonezilla validée sur poste physique |
| [iVentoy](iventoy.md) | Déploiement réseau | Boot PXE pour lancer Clonezilla, Kali ou d'autres ISO du lab |

## HomeLab

Rôle :

- Porter l'infrastructure réseau globale.
- Documenter pfSense, VLAN, WireGuard et CrowdSec.
- Documenter iVentoy comme composant de boot réseau.
- Servir de base aux scénarios offensifs et défensifs.

## HackEth

Rôle :

- Présenter le poste Kali et son intégration dans le HomeLab.
- Expliquer la vision du sous-projet.
- Lier les dépôts techniques associés.
- Regrouper architecture, captures, roadmap et documentation.

## HackEth-Bootstrap

Rôle :

- Installer les outils nécessaires.
- Configurer le shell, les alias et les outils de développement.
- Préparer les wordlists et scripts personnalisés.
- Rendre le poste reproductible en physique ou en VM.

## HackEth-Golden-Image

Rôle :

- Documenter la création de l'image Clonezilla validée.
- Documenter la restauration.
- Stocker les checksums et métadonnées.
- Publier les métadonnées non sensibles de l'image validée.
- Documenter la validation post-restauration sur poste physique.
- Indiquer l'emplacement externe de l'image.
- Éviter de publier une image disque lourde ou sensible dans GitHub.

## iVentoy

Rôle :

- Fournir un boot réseau PXE dans le HomeLab.
- Démarrer Clonezilla Live sans clé USB.
- Démarrer une ISO Kali Linux pour installation ou maintenance.
- Centraliser les ISO utiles au laboratoire.
- Faciliter les opérations de restauration et de reconstruction.

Documentation détaillée : [iVentoy](iventoy.md).
