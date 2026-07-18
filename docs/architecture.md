# Architecture

HackEth est un poste Kali Linux utilisé comme machine offensive contrôlée dans le projet HomeLab.

Le poste est actuellement physique, mais la documentation doit aussi permettre une installation en machine virtuelle. Cela rend le projet plus utile pour une personne souhaitant reproduire l'environnement.

## Positionnement

HackEth est un sous-projet logique du HomeLab, publié dans un dépôt séparé pour conserver une organisation propre sur GitHub.

```text
HomeLab
|
|-- VLAN 10 - ADMIN
|-- VLAN 20 - DEV
|-- VLAN 30 - HACKETH
|    |
|    `-- Kali Linux / HackEth
|
`-- iVentoy / boot réseau PXE
```

## Architecture réseau

```text
Internet
   |
Accès WAN
   |
pfSense
   |
Switch managé
   |
   |-- VLAN 10 ADMIN
   |-- VLAN 20 DEV
   |-- VLAN 30 HACKETH
   |    |
   |    `-- Kali Linux / HackEth
   |
   `-- Service iVentoy / ISO réseau
```

Le schéma Mermaid associé est disponible dans : [`diagrams/architecture.mmd`](../diagrams/architecture.mmd).

## Intégration avec HomeLab

- pfSense assure le routage, le filtrage et le contrôle des flux inter-VLAN.
- Le VLAN 30 est dédié au poste HackEth.
- WireGuard sécurise l'accès distant d'administration.
- CrowdSec et les logs pfSense participent à la détection et à l'analyse.
- iVentoy facilite le démarrage réseau de Clonezilla, Kali ou d'autres ISO utiles au laboratoire.
- Les simulations offensives restent limitées à l'environnement de laboratoire.

## Déploiement avec iVentoy

iVentoy est utilisé comme composant de boot réseau PXE dans le HomeLab.

Il permet de :

- démarrer Clonezilla Live sans clé USB ;
- lancer une ISO Kali Linux pour installation ou maintenance ;
- faciliter la restauration de la Golden Image HackEth ;
- centraliser les ISO utiles au laboratoire ;
- accélérer les opérations de reconstruction ou de dépannage.

La documentation détaillée est disponible ici : [iVentoy](iventoy.md).

## Cibles de déploiement

### Poste physique

- Environnement principal HackEth.
- Utilisé pour les interactions réelles avec le HomeLab.
- Sauvegarde via Golden Image Clonezilla validée.

### Machine virtuelle

- Environnement cible pour les tests reproductibles.
- Utile pour les démonstrations et les contributeurs.
- Reconstructible via HackEth-Bootstrap.

## Principes de conception

- Garder un environnement reproductible.
- Ne pas publier de secrets, données personnelles ou images disque dans GitHub.
- Documenter les choix techniques importants.
- Séparer la vitrine, l'automatisation et la restauration.
- Limiter les activités offensives aux cibles autorisées.
