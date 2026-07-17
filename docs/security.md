# Notes de sécurité

Ce projet touche à des sujets sensibles : outils offensifs, sauvegarde système, configuration réseau et images disque.

Les règles suivantes doivent être respectées avant publication.

## Ne pas publier

- Clés SSH privées.
- Clés VPN.
- Adresses IP publiques réelles.
- Mots de passe ou hash de mots de passe.
- Profils ou historiques de navigateur.
- Documents personnels.
- Images disque Clonezilla complètes dans GitHub.
- Adresses MAC internes non anonymisées.
- Exports pfSense non anonymisés.

## Règles pour la Golden Image

- Stocker l'image en dehors de GitHub.
- Publier uniquement la documentation, les métadonnées et les checksums.
- Vérifier l'intégrité SHA-256 avant et après transfert.
- Conserver une copie privée hors ligne.
- Documenter la restauration étape par étape.

## Règles pour les outils offensifs

- Utiliser les outils uniquement dans des environnements autorisés.
- Limiter les tests au HomeLab ou à des cibles explicitement autorisées.
- Ne pas publier de résultats d'exploitation contre des systèmes tiers.
- Indiquer clairement que les simulations sont réalisées en laboratoire contrôlé.

## Hygiène du dépôt

- Relire les captures avant publication.
- Masquer les adresses IP si nécessaire.
- Masquer les noms d'utilisateur si nécessaire.
- Éviter tout secret dans l'historique Git.
- Utiliser `.gitignore` pour les fichiers locaux et exports temporaires.
