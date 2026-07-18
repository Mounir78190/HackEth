# HackEth

[![Kali Linux](https://img.shields.io/badge/Kali-Linux-blue)](https://www.kali.org/)
[![Cybersecurity](https://img.shields.io/badge/Cybersecurity-Lab-red)](#)
[![HomeLab](https://img.shields.io/badge/HomeLab-pfSense-orange)](https://github.com/Mounir78190/HomeLab)
[![Statut](https://img.shields.io/badge/statut-initialis%C3%A9-blue)](#)
[![Version](https://img.shields.io/badge/version-0.1.0-blue)](VERSION)
[![Licence](https://img.shields.io/badge/licence-MIT-green)](LICENSE)

HackEth est le dépôt vitrine de mon poste de travail cybersécurité basé sur Kali Linux.

Ce projet est un enfant logique du projet [HomeLab](https://github.com/Mounir78190/HomeLab). Il reste un dépôt GitHub séparé afin de garder une organisation claire, mais il dépend directement de l'infrastructure HomeLab pour les scénarios réseau, les tests offensifs contrôlés et l'approche SOC/Blue Team.

Le poste HackEth est actuellement utilisé sur une machine physique. Le projet doit aussi être documenté pour une utilisation en machine virtuelle afin de rester réutilisable par d'autres personnes.

## Objectifs

- Présenter clairement le rôle du poste HackEth dans le HomeLab.
- Valoriser le projet dans une logique de documentation technique claire et réutilisable.
- Fournir une base réutilisable pour reconstruire un poste Kali opérationnel.
- Documenter la stratégie de sauvegarde et restauration via Golden Image Clonezilla.
- Préparer l'automatisation complète avec HackEth-Bootstrap.

## Positionnement dans l'écosystème

```text
HomeLab
|
|-- Infrastructure réseau
|   |-- pfSense firewall
|   |-- Segmentation VLAN
|   |-- WireGuard VPN
|   |-- Détection CrowdSec
|   |-- iVentoy / boot réseau PXE
|   `-- Approche SOC / Blue Team
|
`-- HackEth
    |-- Poste Kali Linux physique
    |-- Compatibilité future VM
    |-- Outils offensifs contrôlés
    |-- Scripts et configuration
    |
    |-- HackEth-Bootstrap
    |   |-- Installation des outils Kali
    |   |-- Configuration shell
    |   |-- Wordlists et utilitaires
    |   |-- Docker et outils de développement
    |   `-- Reconstruction reproductible du poste
    |
    `-- HackEth-Golden-Image
        |-- Documentation image Clonezilla
        |-- Procédure de sauvegarde
        |-- Procédure de restauration
        |-- Vérification SHA-256
        `-- Plan de reprise
```

iVentoy est documenté comme composant de déploiement du HomeLab. Il peut servir à démarrer Clonezilla ou Kali par le réseau, sans dépendre systématiquement d'une clé USB.

## Dépôts liés

| Dépôt | Statut | Rôle |
| --- | --- | --- |
| [HomeLab](https://github.com/Mounir78190/HomeLab) | Existant | Infrastructure réseau, VLAN, pfSense, WireGuard, CrowdSec |
| HackEth | En cours | Dépôt vitrine du poste Kali et point d'entrée du sous-projet |
| [HackEth-Bootstrap](https://github.com/Mounir78190/HackEth-Bootstrap) | Validé sur Kali physique | Automatisation de la reconstruction du poste Kali |
| [HackEth-Golden-Image](https://github.com/Mounir78190/HackEth-Golden-Image) | Initialisé | Documentation de sauvegarde/restauration Clonezilla |
| iVentoy | À documenter | Boot réseau PXE pour lancer Kali, Clonezilla ou d'autres ISO du lab |

## Architecture cible

```text
Internet
   |
Accès WAN / routeur domestique
   |
pfSense Firewall
   |
Trunk VLAN 802.1Q
   |
Switch managé
   |
   |-- VLAN 10 - ADMIN
   |-- VLAN 20 - DEV
   `-- VLAN 30 - HACKETH
        |
        `-- Poste Kali Linux / HackEth
```

Un schéma Mermaid est disponible ici : [diagrams/architecture.mmd](diagrams/architecture.mmd).

## Outils prévus

Périmètre initial pour HackEth-Bootstrap :

- Nmap
- Burp Suite
- Gobuster
- FFUF
- Hydra
- NetExec
- BloodHound
- Docker
- Visual Studio Code
- Python
- Git
- ZSH
- Wordlists
- Scripts et alias personnalisés

## Déploiement réseau

iVentoy est prévu comme composant de boot réseau dans le HomeLab.

Usages envisagés :

- démarrer Clonezilla Live par PXE ;
- démarrer une ISO Kali Linux ;
- faciliter les restaurations de la Golden Image ;
- limiter la dépendance aux clés USB ;
- centraliser les ISO utiles au laboratoire.

## Documentation

- [Architecture](docs/architecture.md)
- [Structure des dépôts](docs/repositories.md)
- [Roadmap](docs/roadmap.md)
- [Notes de sécurité](docs/security.md)
- [Captures d'écran](docs/screenshots.md)
- [Publication GitHub](docs/publishing.md)

## Version

Version actuelle : `0.1.0`

- [Changelog](CHANGELOG.md)
- [Licence](LICENSE)
- [Contribution](CONTRIBUTING.md)

## Statut du projet

Phase actuelle : écosystème initialisé avec Bootstrap validé sur Kali physique.

Prochaines étapes :

- Finaliser la documentation du dépôt HackEth.
- Ajouter des captures anonymisées.
- Tester HackEth-Bootstrap sur Kali VM.
- Enrichir le dépôt HackEth-Golden-Image avec les métadonnées de l'image validée.
- Ajouter les screenshots utiles dans les trois dépôts.
- Rédiger ensuite une version anglaise traduite et corrigée.

## Auteur

Mounir KOUSKOUS  
Opérateur Cybersécurité | SOC Junior | Administration Système et Réseau

LinkedIn : https://www.linkedin.com/in/mounir-kouskous/

## Avertissement

Ce projet est destiné à un usage pédagogique, documentaire et laboratoire contrôlé. Les outils et techniques offensives doivent uniquement être utilisés sur des systèmes personnels ou explicitement autorisés.
