# Publication GitHub

Ce document sert de checklist avant publication du dépôt HackEth sur GitHub.

## Avant le premier push

- Vérifier que la documentation est en français correct.
- Vérifier que les captures sont anonymisées.
- Vérifier que le fichier `.gitignore` couvre les images disque et secrets.
- Vérifier qu'aucune clé SSH, VPN ou configuration sensible n'est présente.
- Vérifier que le dépôt ne contient pas d'image Clonezilla.
- Vérifier que les liens vers HomeLab sont corrects.
- Vérifier que la licence est présente.
- Vérifier que le changelog est initialisé.

## Commandes prévues

```bash
git init
git add .
git commit -m "Initial HackEth showcase repository"
git branch -M main
git remote add origin https://github.com/Mounir78190/HackEth.git
git push -u origin main
```

## Après publication

- Ajouter une description courte au dépôt GitHub.
- Ajouter les topics GitHub.
- Vérifier le rendu du README.
- Vérifier le rendu du schéma Mermaid.
- Créer les dépôts HackEth-Bootstrap et HackEth-Golden-Image lorsque la structure est validée.

## Topics suggérés

```text
cybersecurity
homelab
kali-linux
pfsense
vlan
blueteam
offensive-security
soc
clonezilla
automation
```
