# iVentoy

iVentoy est documenté comme composant de boot réseau PXE dans l'écosystème HomeLab/HackEth.

Il permet de démarrer des ISO depuis le réseau, sans dépendre systématiquement d'une clé USB. Dans le cadre HackEth, il sert principalement à lancer Clonezilla Live, Kali Linux ou d'autres outils de maintenance utiles au laboratoire.

## Rôle dans l'écosystème

```text
HomeLab
|
|-- pfSense
|-- VLAN
|-- Services réseau
|
`-- iVentoy
    |-- ISO Clonezilla Live
    |-- ISO Kali Linux
    |-- ISO de maintenance
    `-- Boot PXE pour postes physiques ou VM compatibles
```

## Objectifs

- Centraliser les ISO utilisées dans le lab.
- Démarrer Clonezilla Live sans clé USB.
- Faciliter la restauration de la Golden Image HackEth.
- Préparer une installation Kali propre avant utilisation de HackEth-Bootstrap.
- Accélérer les opérations de maintenance ou de dépannage.

## Cas d'usage

### Restauration HackEth

```text
Poste HackEth
|
|-- Boot PXE
|-- iVentoy
|-- ISO Clonezilla Live
|-- Accès à l'image Clonezilla validée
`-- Restauration du disque
```

### Installation Kali

```text
Poste physique ou VM
|
|-- Boot PXE
|-- iVentoy
|-- ISO Kali Linux
|-- Installation propre
`-- Exécution de HackEth-Bootstrap
```

### Maintenance

```text
Poste à diagnostiquer
|
|-- Boot PXE
|-- iVentoy
|-- ISO de diagnostic ou maintenance
`-- Intervention sans support USB dédié
```

## ISO recommandées

- Clonezilla Live.
- Kali Linux Installer.
- Kali Linux Live.
- Debian netinst ou live ISO si nécessaire.
- ISO de diagnostic matériel si utile au lab.

## Prérequis

- Service iVentoy fonctionnel dans le HomeLab.
- Poste cible compatible avec le boot PXE.
- Connectivité réseau entre le poste cible et le service iVentoy.
- ISO placées dans le répertoire prévu par iVentoy.
- DHCP ou configuration réseau cohérente avec le boot PXE.

## Points d'attention réseau

- Vérifier que le poste cible reçoit une configuration réseau au boot.
- Vérifier que le VLAN utilisé autorise l'accès au service iVentoy.
- Vérifier que pfSense ne bloque pas les flux nécessaires au boot réseau.
- Vérifier que le switch managé laisse passer le trafic attendu.
- Éviter d'exposer iVentoy hors du périmètre HomeLab.

## Sécurité

iVentoy donne accès à des ISO capables d'installer, restaurer ou modifier des systèmes. Il doit donc rester limité à l'environnement de laboratoire.

Bonnes pratiques :

- Ne pas exposer l'interface iVentoy publiquement.
- Limiter l'accès au réseau de lab.
- Conserver uniquement des ISO vérifiées.
- Supprimer les ISO inutiles.
- Documenter les ISO présentes.
- Éviter de laisser un poste sensible démarrer en PXE sans contrôle.

## Validation actuelle

Statut actuel : documenté et utilisé comme option de boot réseau pour Clonezilla.

Éléments validés :

- interface iVentoy fonctionnelle ;
- ISO Clonezilla Live visible dans iVentoy ;
- boot Clonezilla via iVentoy documenté ;
- restauration HackEth documentée avec option iVentoy/PXE.

Éléments à compléter :

- documenter l'emplacement exact du service dans le HomeLab sans exposer d'information sensible ;
- ajouter une procédure pas à pas iVentoy si nécessaire ;
- tester le boot d'une ISO Kali via iVentoy ;
- tester le scénario en VM.

## Captures associées

Les captures liées à iVentoy sont stockées dans le dépôt `HackEth-Golden-Image` :

- `screenshots/iventoy/iventoy-clonezilla-boot-information.png`

## Lien avec les autres dépôts

- `HackEth` documente le rôle global d'iVentoy dans l'écosystème.
- `HackEth-Golden-Image` documente l'utilisation d'iVentoy pour démarrer Clonezilla.
- `HackEth-Bootstrap` intervient après installation Kali, pas pendant le boot PXE.
