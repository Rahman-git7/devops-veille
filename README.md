# 🔍 DevOps Veille Automatisée

> **Veille technologique DevOps 100% automatisée avec GitHub Actions**

Recevez chaque lundi matin un résumé des actualités DevOps les plus importantes, directement dans vos notifications GitHub. Fini la recherche manuelle d'informations !

## ✨ Fonctionnalités

- 📰 **Agrégation automatique** de 5 sources DevOps majeures
- 📊 **Résumé hebdomadaire** généré chaque lundi à 8h
- 📧 **Notifications email** via GitHub Issues
- 🏷️ **Organisation** avec labels et historique complet
- ⚡ **Zero maintenance** - configurez une fois, oubliez pour toujours

## 📋 Sources suivies

- **DevOps'ish** - Actualités DevOps générales
- **Kubernetes Blog** - Évolutions de l'écosystème K8s
- **Docker Blog** - Nouveautés conteneurisation
- **HashiCorp Blog** - Terraform, Vault, Consul...
- **AWS DevOps Blog** - Pratiques cloud AWS

## 🚀 Quick Setup

### 1. Cloner ce repo ou créer le vôtre
```bash
git clone https://github.com/VOTRE-USER/devops-veille.git
cd devops-veille
```

### 2. Ajouter le workflow GitHub Actions
Créez `.github/workflows/devops-veille.yml` avec le contenu fourni dans ce repo.

### 3. Configurer les permissions
- Repo **Settings** → **Actions** → **General**
- **Workflow permissions** : Cochez "Read and write permissions"
- Cochez "Allow GitHub Actions to create and approve pull requests"

### 4. Créer le label (optionnel)
- **Issues** → **Labels** → **New label**
- Nom : `veille` | Couleur : au choix

### 5. Activer les notifications
- **Settings personnelles** : github.com/settings/notifications
- Vérifiez que "Issues" est activé pour les emails

## ⚙️ Configuration

### Changer la fréquence
Modifiez le cron dans le workflow :
```yaml
schedule:
  - cron: '0 8 * * 1'  # Lundi 8h (par défaut)
  - cron: '0 18 * * 5'  # Vendredi 18h (exemple)
```

### Ajouter des sources RSS
Ajoutez des feeds dans la liste Python :
```python
feeds = [
    'https://devopsish.com/index.xml',
    'https://kubernetes.io/feed.xml',
    # Ajoutez votre source ici
    'https://example.com/feed.xml'
]
```

### Personnaliser le résumé
Modifiez le template markdown dans le script Python pour adapter le format.

## 📊 Utilisation

Une fois configuré :

1. **Chaque lundi à 8h** : Le workflow se déclenche automatiquement
2. **Une issue GitHub** est créée avec le résumé de la semaine
3. **Vous recevez un email** de notification
4. **Lecture en 2-3 minutes** pendant votre café ☕

### Déclenchement manuel
```bash
# Via l'interface GitHub
Actions → DevOps Veille Automatique → Run workflow

# Ou modifiez un fichier et poussez pour tester
```

## 📈 Exemple de résumé

```markdown
# DevOps Veille - 2025-07-17

## 📈 Actualités cette semaine

### Announcing the end of support for Node.js 18.x in AWS CDK
**Source:** AWS DevOps & Developer Productivity Blog
**Résumé:** On November 30th, 2025, the AWS Cloud Development Kit (CDK) will no longer support Node.js 18.x...
**Lien:** https://aws.amazon.com/blogs/devops/announcing-the-end-of-support-for-node-js-18-x-in-aws-cdk/
```

## 🛠️ Dépannage

### Le workflow ne se déclenche pas automatiquement
- Vérifiez les permissions du repo
- Les nouveaux repos peuvent avoir un délai de 24-48h
- Testez le déclenchement manuel d'abord

### Pas de notifications email
- Vérifiez github.com/settings/notifications
- Regardez vos spams/promotions
- Cliquez "Subscribe" sur une issue de test

### Erreur de parsing RSS
- Certains feeds peuvent être temporairement indisponibles
- Le workflow continue avec les sources disponibles

## 🤝 Contribution

- ⭐ **N'hésitez pas à star le projet, ça fait toujours plaisir !**
- Fork le projet
- Ajoutez des sources RSS pertinentes
- Améliorez le format de sortie
- Proposez des fonctionnalités via les Issues

## 📄 Licence

MIT License - Utilisez, modifiez, partagez librement !

---

**⏱️ Temps de setup : 5 minutes | Temps hebdomadaire : 2-3 minutes de lecture**

*Arrêtez de chercher les actualités DevOps - laissez-les venir à vous !*